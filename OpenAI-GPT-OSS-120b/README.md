# AMD Dev Cloud MX300 - OpenAI GPT OSS 120b

This guide provides instructions for the OpenAI GPT OSS 120b vLLM inference environment running on an AMD Dev Cloud MX300 instance.

After provisioning a new droplet with the OpenAI GPT OSS 120b image, SSH into the droplet as root. The welcome message will provide instructions and login credentials.

The following three interfaces are pre-configured with the Docker image:

  * **Open a WebUI interface in the browser by visiting:**

      * `http://<Your-Droplet-IP>`
      * To authenticate in the WebUI, use the email and password provided in the welcome message.

  * **Or access the vLLM inferencing API directly at:**

      * `http://<Your-Droplet-IP>:8000`
      * The Bearer Token for the GPT OSS inferencing API will be in the welcome message.

<!-- end list -->

```
curl --request POST \
  --url http://<Your-Droplet-IP>:8000/v1/chat/completions \
  --header 'Authorization: Bearer <Your-Bearer-Token>' \
  --header 'Content-Type: application/json' \
  --data '{
    "model": "openai/gpt-oss-120b",
    "messages": [
      {"role": "user", "content": "What is the capital of France?"}
    ]
  }'
```

  * **Or from within this Droplet:**

<!-- end list -->

```
  curl -X POST "http://localhost:8001/v1/chat/completions" \
    -H "Content-Type: application/json" \
    --data '{
      "model": "openai/gpt-oss-120b",
      "messages": [
        {
          "role": "user",
          "content": "What is the capital of France?"
        }
      ]
    }'
```

