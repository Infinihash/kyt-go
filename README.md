# kyt-go

Official Go SDK for the [Infinihash KYT API](https://kyt.infinihash.com/docs).

> **Status: Alpha** — API is stable; SDK wrapper is actively being built. Full docs coming soon.

## Installation

```bash
go get github.com/infinihash/kyt-go
```

## Quick Start

```go
package main

import (
    "fmt"
    "github.com/infinihash/kyt-go/kyt"
)

func main() {
    client := kyt.New("your-api-key")

    result, err := client.Screen(kyt.ScreenRequest{
        Type:  "wallet",
        Value: "0x722122dF12D4e14e13Ac3b6895a86e84145b6967",
        Chain: "ethereum",
    })
    if err != nil {
        panic(err)
    }

    fmt.Println(result.RiskLevel)  // critical
    fmt.Println(result.Action)     // block
}
```

## Features

- Wallet and transaction screening
- SAR narrative generation
- Case management
- Webhook subscription helpers
- Context-aware async calls

## Documentation

Full API reference at [kyt.infinihash.com/docs](https://kyt.infinihash.com/docs).

## Support

Questions? [support@infinihash.com](mailto:support@infinihash.com)

## License

MIT © Infinihash LLC
