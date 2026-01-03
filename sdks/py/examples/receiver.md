# Receiver

When receiving a message from QStash, you should [verify the signature](/qstash/howto/signature).
The QStash Python SDK provides a helper function for this.

```python  theme={"system"}
from qstash import Receiver

receiver = Receiver(
    current_signing_key="YOUR_CURRENT_SIGNING_KEY",
    next_signing_key="YOUR_NEXT_SIGNING_KEY",
)

# ... in your request handler

signature, body = req.headers["Upstash-Signature"], req.body

receiver.verify(
    body=body,
    signature=signature,
    url="YOUR-SITE-URL",
)
```


---

> To find navigation and other pages in this documentation, fetch the llms.txt file at: https://upstash.com/docs/llms.txt