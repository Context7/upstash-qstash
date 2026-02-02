> ## Documentation Index
> Fetch the complete documentation index at: https://upstash.com/docs/llms.txt
> Use this file to discover all available pages before exploring further.

# Queues

#### Create a queue with parallelism

```python  theme={"system"}
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")

queue_name = "upstash-queue"
client.queue.upsert(queue_name, parallelism=2)

print(client.queue.get(queue_name))
```

#### Delete a queue

```python  theme={"system"}
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")

queue_name = "upstash-queue"
client.queue.delete(queue_name)
```

<Warning>
  Resuming or creating a queue may take up to a minute.
  Therefore, it is not recommended to pause or delete a queue during critical operations.
</Warning>

#### Pause/Resume a queue

```python  theme={"system"}
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")

queue_name = "upstash-queue"
client.queue.upsert(queue_name, parallelism=1)

client.queue.pause(queue_name)

queue = client.queue.get(queue_name)
print(queue.paused) # prints True

client.queue.resume(queue_name)
```

<Warning>
  Resuming or creating a queue may take up to a minute.
  Therefore, it is not recommended to pause or delete a queue during critical operations.
</Warning>
