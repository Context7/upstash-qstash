On this page
Search queries with filters only return documents which have the content matching with the filter. Upstash Search allows you to filter by content keys which have the following value types:
  * string
  * number
  * boolean
  * object
  * array

Filtering is implemented as a combination of in and post-filtering. Every query is assigned a filtering budget, determining the number of candidate documents that can be compared against the filter during query execution. If this budget is exceeded, the system fallbacks into post-filtering. Therefore, with highly selective filters, fewer than `topK` documents may be returned.
* * *
## 
​
Filter Syntax
A filter has a syntax that resembles SQL, which consists of operators on content keys and boolean operators to combine them. Assuming you have content like below:
Copy
Ask AI
```
{
  // 👇 searchable and filterable
  content: {
    name: "Wireless Headphones",
    description: "Noise-cancelling bluetooth headphones",
    brand: "Sony",
    category: "Electronics",
    warehouse_location: "A3-15",
    in_stock: 3
  },
  // 👇 not searchable, for reference only
  metadata: {
    sku: "AT-WH-001",
    supplier_id: "SUP-123",
  }
}

```

Filter documents like so:
  * Python
  * TypeScript


Copy
Ask AI
```
scores = index.search(
    query="sony headphones",
    filter="warehouse_location = 'A3-15'",
)

```

### 
​
TypeSafe Filters (TypeScript)
In our TypeScript SDK, we support a typesafe way to build filters:
Copy
Ask AI
```
import { Search } from "@upstash/search";

type IndexContent = {
  name: string;
  description: string;
  brand: string;
  category: string[];
  warehouse_location: string;
  in_stock: number;
};

const client = new Client({ ... });
const index = client.index<IndexContent>("products");

const searchResults = await index.search({
  query: "sony headphones",
  filter: { category: { contains: 'electronics' } },
});

```

Note that we passed `IndexContent` as a type parameter to the `index` method. This allows the SDK to infer the type of the content, enabling type-safe filters.
You can use the `AND` and `OR` operators to build complex filters.
AND
OR
Nested AND/OR
Copy
Ask AI
```
const searchResults = await index.search({
  query: "sony headphones",
  filter: {
    AND: [
      { warehouse_location: { equals: 'A3-15' } },
      { in_stock: { greaterThan: 0 } }
    ]
  },
});

```

All the operations below except for filtering array elements and nested objects are supported in the typesafe filters.
* * *
## 
​
Operators
#### 
​
Equals (=)
The `equals` operator filters content whose values are equal to the given literal. It is applicable to _string_ , _number_ , and _boolean_ values.
Copy
Ask AI
```
warehouse_location = 'A3-15' AND in_stock = 3

```

* * *
#### 
​
Not Equals (!=)
The `not equals` operator filters content whose values are not equal to the given literal. It is applicable to _string_ , _number_ , and _boolean_ values.
Copy
Ask AI
```
warehouse_location != 'A3-15' AND in_stock != 3

```

* * *
#### 
​
Less Than (<)
The `less than` operator filters content whose values are less than the given literal. It is applicable to _number_ values.
Copy
Ask AI
```
in_stock < 3

```

* * *
#### 
​
Less Than or Equals (<=)
The `less than or equals` operator filters content whose values are less than or equal to the given literal. It is applicable to _number_ values.
Copy
Ask AI
```
in_stock <= 3

```

* * *
#### 
​
Greater Than (>)
The `greater than` operator filters content whose values are greater than the given literal. It is applicable to _number_ values.
Copy
Ask AI
```
in_stock > 3

```

* * *
#### 
​
Greater Than or Equals (>=)
The `greater than or equals` operator filters content whose values are greater than or equal to the given literal. It is applicable to _number_ values.
Copy
Ask AI
```
in_stock >= 3

```

* * *
#### 
​
Glob
The `glob` operator filters content whose values match with the given UNIX glob pattern. It is applicable to _string_ values. It is a case sensitive operator. The glob operator supports the following wildcards:
  * `*` matches zero or more characters.
  * `?` matches exactly one character.
  * `[]` matches one character from the list 
    * `[abc]` matches either `a`, `b`, or `c`.
    * `[a-z]` matches one of the range of characters from `a` to `z`.
    * `[^abc]` matches any one character other than `a`, `b`, or `c`.
    * `[^a-z]` matches any one character other than `a` to `z`.

For example, the filter below would only match with warehouse locations whose first character is `A` or `B`.
Copy
Ask AI
```
warehouse_location GLOB '[AB]*'

```

* * *
#### 
​
Not Glob
The `not glob` operator filters content whose values do not match with the given UNIX glob pattern. It is applicable to _string_ values. It has the same properties with the glob operator. For example, the filter below would only match with warehouse locations whose first character is anything other than `A`.
Copy
Ask AI
```
warehouse_location NOT GLOB 'A*'

```

* * *
#### 
​
In
The `in` operator filters content whose values are equal to any of the given literals. It is applicable to _string_ , _number_ , and _boolean_ values.
Copy
Ask AI
```
country IN ('Germany', 'Turkey', 'France')

```

Semantically, it is equivalent to equals operator applied to all of the given literals with `OR` boolean operator in between:
Copy
Ask AI
```
country = 'Germany' OR country = 'Turkey' OR country = 'France'

```

* * *
#### 
​
Not In
The `not in` operator filters content whose values are not equal to any of the given literals. It is applicable to _string_ , _number_ , and _boolean_ values.
Copy
Ask AI
```
economy.currency NOT IN ('USD', 'EUR')

```

Semantically, it is equivalent to not equals operator applied to all of the given literals with `AND` boolean operator in between:
Copy
Ask AI
```
economy.currency != 'USD' AND economy.currency != 'EUR'

```

* * *
#### 
​
Contains
The `contains` operator filters content whose values contain the given literal. It is applicable to _array_ values.
Copy
Ask AI
```
economy.major_industries CONTAINS 'Tourism'

```

* * *
#### 
​
Not Contains
The `not contains` operator filters content whose values do not contain the given literal. It is applicable to _array_ values.
Copy
Ask AI
```
economy.major_industries NOT CONTAINS 'Steel Production'

```

* * *
#### 
​
Has Field
The `has field` operator filters content which have the given JSON field.
Copy
Ask AI
```
HAS FIELD geography.coordinates

```

* * *
#### 
​
Has Not Field
The `has not field` operator filters content which do not have the given JSON field.
Copy
Ask AI
```
HAS NOT FIELD geography.coordinates.longitude

```

* * *
### 
​
Boolean Operators
Operators above can be combined with `AND` and `OR` boolean operators to form compound filters.
Copy
Ask AI
```
country = 'Turkey' AND population > 10000000

```

Boolean operators can be grouped with parentheses to have higher precedence.
Copy
Ask AI
```
country = 'Turkey' AND (population > 10000000 OR is_capital = false)

```

When no parentheses are provided in ambiguous filters, `AND` will have higher precedence than `OR`. So, the filter
Copy
Ask AI
```
country = 'Turkey' AND population > 10000000 OR is_capital = false

```

would be equivalent to
Copy
Ask AI
```
(country = 'Turkey' AND population > 10000000) OR is_capital = false

```

* * *
### 
​
Filtering Nested Objects
It is possible to filter nested object fields by referencing them with the `.` accessor. Nested fields can be at arbitrary depths, so more than one `.` accessor can be used in the same identifier.
Copy
Ask AI
```
economy.currency != 'USD' AND geography.coordinates.latitude >= 35.0

```

* * *
### 
​
Filtering Array Elements
Apart from the `CONTAINS` and `NOT CONTAINS` operators, individual array elements can also be filtered by referencing them with the `[]` accessor by their indexes. Indexing is zero based.
Copy
Ask AI
```
economy.major_industries[0] = 'Tourism'

```

Also, it is possible to index from the back using the `#` character with negative values. `#` can be thought as the number of elements in the array, so `[#-1]` would reference the last element.
Copy
Ask AI
```
economy.major_industries[#-1] = 'Finance'

```

* * *
### 
​
Miscellaneous
  * Identifiers (the left side of the operators) should be of the form `[a-zA-Z_][a-zA-Z_0-9.[\]#-]*`. In simpler terms, they should start with characters from the English alphabet or `_`, and can continue with same characters plus numbers and other accessors like `.`, `[0]`, or `[#-1]`.
  * The string literals (strings in the right side of the operators) can be either single or double quoted.
  * Boolean literals are represented as `1` or `0`.
  * The operators, boolean operators, and boolean literals are case insensitive.


Was this page helpful?
YesNo
Suggest editsRaise issue
Content and MetadataReranking
Assistant
Responses are generated using AI and may contain mistakes.
