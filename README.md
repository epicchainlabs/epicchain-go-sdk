<p align="center">
  <img 
    src="http://res.cloudinary.com/vidsy/image/upload/v1503160820/CoZ_Icon_DARKBLUE_200x178px_oq0gxm.png" 
    width="125px"
  >
</p>

<h1 align="center">epicchain-go-sdk</h1>

<p align="center">
  Golang SDK for the <b>EpicChain</b> blockchain.
</p>


## What?

- Client for interacting with a node on the [EpicChain](http://epic-chain.org/) blockchain.
- Retrieve data and send actions.
- Fully tested [Golang](https://golang.org/) package.
- Aimed to help other developers build applications for the NEO ecosystem.
- Written using the standard library, without 3rd party packages. 

## Quick Start

```
go get github.com/epicchainlabs/epicchain-go-sdk
```

```golang
package main

import (
  "log"

  "github.com/epicchainlabs/epicchain-go-sdk/epicchain"
)

func main() {
  nodeURI := "http://testnet1-seed.epic-chain.org:20111"
  client := epicchain.NewClient(nodeURI)

  ok := client.Ping()
  if !ok {
    log.Fatal("Unable to connect to EpicChain node")
  }

  block, err := client.GetBlockByHash(
    "3f0b498c0d57f73c674a1e28045f5e9a0991f9dac214076fadb5e6bafd546170",
  )
  if err != nil {
    log.Fatal(err)
  }

  log.Printf("Block found, index is: %d", block.Index)
}
```



## CLI



Debugging a EpicChain public and private key pair is a common task when interacting with the blockchain.
Make use of the **epicchain-go-sdk** CLI to help with this process:

```
./epicchain-go-sdk --wif KxQREAjBL6Ga8dw9rPN45pwoZ5dxhAQacEajQke6qmpB7DW6nAWE
```

This will output the **full details** about the key pair. See [releases](https://github.com/epicchainlabs/epicchain-go-sdk/releases) to download the CLI.

## Help

- Open a new [issue](https://github.com/epicchainlabs/epicchain-go-sdk/issues/new) if you encountered a problem.
- Submitting PRs to the project is always welcome! 🎉
- Check the [Changelog](https://github.com/CityOfZion/neo-go-sdk/blob/master/CHANGELOG.md) for recent changes.

