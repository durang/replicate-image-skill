# Replicate API Examples

## Setup
```python
import os
import replicate

# Set your Replicate API token from environment
os.environ['REPLICATE_API_TOKEN'] = os.environ.get('REPLICATE_API_TOKEN')
```

## Nano Banana 2 - Basic Image Generation

```python
import os
import replicate

os.environ['REPLICATE_API_TOKEN'] = os.environ.get('REPLICATE_API_TOKEN')

# Generate image
output = replicate.run(
    "google/nano-banana-2",
    input={
        "prompt": "A serene sunset over mountains, photorealistic, 4K",
        "aspect_ratio": "16:9",
        "output_format": "jpg",
        "output_quality": 90
    }
)
print(output)  # Returns URL like https://replicate.delivery/...
```

## Nano Banana 2 - With Reference Images

```python
output = replicate.run(
    "google/nano-banana-2",
    input={
        "prompt": "Transform this into a cyberpunk style",
        "image": "https://example.com/input.jpg",  # URL or file
        "aspect_ratio": "1:1"
    }
)
```

## GPT Image 1 - Basic Generation

```python
import os
import replicate

os.environ['REPLICATE_API_TOKEN'] = os.environ.get('REPLICATE_API_TOKEN')

output = replicate.run(
    "openai/gpt-image-1",
    input={
        "prompt": "A futuristic city with flying cars, digital art style",
        "openai_key": os.environ.get('OPENAI_API_KEY')  # Required - your OpenAI API key
    }
)
print(output)
```

## GPT Image 1 - With Image Input (Editing)

```python
output = replicate.run(
    "openai/gpt-image-1",
    input={
        "prompt": "Change the background to a tropical beach",
        "image": "https://example.com/photo.jpg",
        "openai_key": os.environ.get('OPENAI_API_KEY'),
        "moderation": "low"  # Optional: "auto" or "low"
    }
)
```

## Full Script Template

```python
#!/usr/bin/env python3
import os
import replicate

def generate_image(prompt, model="nano-banana-2", **kwargs):
    """Generate image using Replicate."""
    
    token = os.environ.get('REPLICATE_API_TOKEN')
    if not token:
        raise ValueError("REPLICATE_API_TOKEN not set")
    
    os.environ['REPLICATE_API_TOKEN'] = token
    
    model_id = "google/nano-banana-2" if model == "nano-banana-2" else "openai/gpt-image-1"
    
    # Build input
    if model == "gpt-image-1":
        if 'openai_key' not in kwargs:
            raise ValueError("GPT Image 1 requires openai_key")
        input_params = {"prompt": prompt, "openai_key": kwargs.pop('openai_key')}
    else:
        input_params = {"prompt": prompt}
    
    # Add additional params
    input_params.update(kwargs)
    
    output = replicate.run(model_id, input=input_params)
    
    # Output is a list of URLs
    if isinstance(output, list):
        return output[0]
    return output

if __name__ == "__main__":
    import sys
    
    if len(sys.argv) < 2:
        print("Usage: python3 generate.py \"prompt text\"")
        sys.exit(1)
    
    prompt = sys.argv[1]
    result = generate_image(prompt, model="nano-banana-2", aspect_ratio="16:9")
    print(f"Generated: {result}")
```

## Common Parameters

### Nano Banana 2
| Parameter | Options | Default |
|-----------|---------|---------|
| aspect_ratio | 1:1, 2:3, 3:2, 3:4, 4:3, 4:5, 5:4, 9:16, 16:9, 21:9, 1:4, 4:1, 1:8, 8:1 | 1:1 |
| output_format | jpg, png | jpg |
| output_quality | 1-100 | 90 |
| image | URL or base64 | None |
| prompt | string | required |

### GPT Image 1
| Parameter | Options | Default |
|-----------|---------|---------|
| prompt | string | required |
| image | URL | None (text-only generation) |
| openai_key | sk-... | required |
| moderation | auto, low | auto |

## Output Handling

Replicate returns a list of output URLs. Typically one URL per generation:

```python
output = replicate.run("google/nano-banana-2", input={"prompt": "..."})
# output: ["https://replicate.delivery/..."]

for url in output:
    print(url)
```

## Async/Poll for Long Jobs

Some predictions take time. Use the prediction ID to poll:

```python
# Create prediction
prediction = replicate.predictions.create(
    version="...",
    input={"prompt": "..."}
)

# Poll until complete
while prediction.status not in ["succeeded", "failed", "canceled"]:
    prediction.reload()
    time.sleep(1)

if prediction.status == "succeeded":
    print(prediction.output)
```