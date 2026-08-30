# wikipedia_filter

EmergenceSystem filter that searches Wikipedia and returns article snippets as embryos.


<!-- emergence-context -->
Part of **[EmergenceSystem](https://github.com/EmergenceSystem)** — a distributed
discovery network of small, single-source agents. This filter joins the em_pop gossip
mesh and answers `POST /agent/query`; Emquest fans each query out to many filters in
parallel and aggregates the results.

## API

Queries the [Wikipedia Action API](https://en.wikipedia.org/w/api.php) full-text search endpoint. No API key required.

## Input

```json
{"query": "quantum computing"}
```

| Field     | Type    | Default | Description              |
|-----------|---------|---------|--------------------------|
| `query`   | string  | —       | Search term              |
| `value`   | string  | —       | Alias for `query`        |
| `timeout` | integer | `10`    | HTTP timeout in seconds  |

## Output

One embryo per search result:

```json
{
  "properties": {
    "url":    "https://en.wikipedia.org/wiki/Quantum_computing",
    "resume": "Quantum computing is a type of computation...",
    "title":  "Quantum computing",
    "source": "en.wikipedia.org"
  }
}
```

## Capabilities

`wikipedia`, `encyclopedia`, `search`

## Usage

```bash
rebar3 shell
```

## License

Apache-2.0
