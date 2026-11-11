# Serialisera listor

[Listor](../../../grundlaggande/listor-och-arrayer.md#list) i C# serialiseras så länge de är properties.

{% code title="Pokemon.cs" lineNumbers="true" %}
```csharp
class Pokemon
{
  [JsonPropertyName("name")]
  public string Name {get; set;}
  
  [JsonPropertyName("forms")]
  public List<string> Forms {get; set;}
}
```
{% endcode %}

I JSON-kod omges listor av hakparenteser `[]`.

{% code lineNumbers="true" %}
```json
{
  "name": "ditto",
  "forms":
  [
    "Ditto",
    "Exempel"
  ]
}
```
{% endcode %}
