On this page
### 
​
Symptom
The client gets an exception similar to:
Copy
Ask AI
```
ReplyError: ERR max key size exceeded. Limit: X bytes, Actual: Z bytes

```

### 
​
Diagnosis
Size of the key in the request exceeds the max key size limit, which is `32Kb`.
### 
​
Solution
This is a hardcoded limit and cannot be configured per database. You should reduce the key size.
Was this page helpful?
YesNo
Suggest editsRaise issue
ERR max single record size exceededERR DB capacity quota exceeded
Assistant
Responses are generated using AI and may contain mistakes.
