# [vLLM](https://github.com/vllm-project/vllm) demo app for Fly.io


First deploy with:
```
fly launch
```

from there update by running: `fly deploy`

Once deploy, interact with the API at https://$APPNAME.fly.dev/


```
❯ curl https://vllm-demo.fly.dev/v1/completions \
    -H "Content-Type: application/json"  \
    -d '{
        "model": "facebook/opt-125m",
        "prompt": "San Francisco is a",
        "max_tokens": 7,
        "temperature": 0
    }' -s |jq .
{
  "id": "cmpl-b4b03ec33d794a50ba5cf2801d807025",
  "object": "text_completion",
  "created": 1716250075,
  "model": "facebook/opt-125m",
  "choices": [
    {
      "index": 0,
      "text": " great place to live.  I",
      "logprobs": null,
      "finish_reason": "length",
      "stop_reason": null
    }
  ],
  "usage": {
    "prompt_tokens": 5,
    "total_tokens": 12,
    "completion_tokens": 7
  }
}
```
