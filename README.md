# Cards

**Creating document: Allow developer to use our code effeciently**

## Example

#### How to create document in elixir

Go to the mix.exs file add the dependencies

```
{:ex_doc, "~> 0.12"}
```

And install the dependencies by running command from terminal

```
mix deps.get
```

Once this is done you can create module level and function level document using the ex doc it creates a beautifull HTML documentation

To add module level doc add @moduledoc after the module

```
defmodule Cards do
  @moduledoc """
  Provide developer with function to handle deck and create hands
  """
```

To generate the doc run command

```
mix docs
```
