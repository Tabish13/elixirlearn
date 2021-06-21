# Cards

**Pattern Matching: Read a write a file to disk and use pattern matching to detect the status and data**

## Example

#### Code to write file to disk

```
def save(deck, filename)do
  binary = :erlang.term_to_binary(deck)
  File.write(filename, binary)
end
```

Where `:erlang` is used to use the erlang function inside the elixir `term_to_binary` take data convert it to binary string.

File.write takes a file name and a binary to write to the disk.

#### code to read file from disk

```
def load(filename)do
  {status, binary} = File.read(filename)
  case status do
    :ok -> :erlang.binary_to_term(binary)
    :error -> "File does not exist"
  end
end
```

```
Modify the case status and remove the {status, binary}
Pattern matching with case
def load(filename) do
    case File.read(filename) do
      {:ok, binary} -> :erlang.binary_to_term(binary)
      {:error, _reason} -> "File does not exist"
    end
  end
```

### Using Pipe Operators

```
def create_hand(hand_size) do
    deck = Cards.create_deck()
    deck = Cards.shuffle(deck)
    hand = Cards.deal(deck, hand_size)
  end

```

The above code is similar to the below code using the pipe operator
Please pay attention that the deck variable should be the first argument of the function in the piped functions i.e when we call the deal function we dont need to pass deck as it is automatically passed as first argument from the previous function.

```
def create_hand(hand_size) do
    Cards.create_deck()
    |> Cards.shuffle()
    |> Cards.deal(hand_size)
  end
```
