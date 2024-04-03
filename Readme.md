# MockAI

MockAI is a library that allows you to mock AI responses using custom commands suitable for simulating responses during testing without AI inference cost.

## Installation

To install MockAI, use pip:

```
pip install mockai
```

## Usage

To use MockAI, create a configuration file with your command and the respective response path. 

Example configuration file:

```json
  {
    "/default": "mock_responses/default.json",
    "/mycommand": "mock_responses/my_command.json",
  ...
  }
```

Then, import the `mock_completion` and `set_config` from mockai to :

```python
from mockai import mock_completion, set_config

set_config('config.json')
response = mock_completion(model='your-model', messages=[{"role":"user", "content":"/mycommand"}])
print(response)  # output: "Retrieving the output defined in the mock_responses/my_command.json"
```

## Limitations

MockAI does not support streaming at the moment

## License

MockAI is licensed under the [MIT License](LICENSE).