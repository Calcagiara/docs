---
render_macros: true
---

# Create a vLLM Text Function

Define the Function with the text model source URL.

## Parameters

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| project | str | (✓) | Project name. Required only when creating from the library; otherwise **MUST NOT** be set. |
| name | str | ✓ | Name that identifies the object. |
| kind | str | ✓ | Function kind. Must be `vllmserve-text`. |
| uuid | str | | Object ID in UUID4 format. |
| description | str | | Description of the object. |
| labels | list[str] | | List of labels. |
| embedded | bool | | Whether to embed the object in the project. |
| model_name | str | | Name of the model. |
| image | str | | Docker image used to serve the model. |
| url | str | | Model source URL. |
| [adapters](#adapters) | list[dict] | | List of model adapters. |

## Adapters

Adapters are a list of dictionaries with `name` and `url` keys:

```python
adapters = [{"name": "adapter-name", "url": "adapter-url"}]
```

## Example

```python
base_model = project.new_model(
    name="base-model",
    kind="huggingface",
    path="hf://Qwen/Qwen2.5-7B-Instruct"
)

llm_function = project.new_function(
    name="llama32-1b-v2",
    model_name="test-model",
    kind="vllmserve-text",
    url=base_model.key
)
```

{{ page_navigation(("Action", "action.md"), ("Run", "run.md")) }}
