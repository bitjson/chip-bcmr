# Registry Examples

This directory includes several [Bitcoin Cash Metadata Registry](../readme.md) examples. Each example is briefly described below.

## Fungible Token

The [`fungible-token.json` example](./examples/fungible-token.json) demonstrates how the issuer of a single kind of fungible token might publish information about the token.

The registry includes only one identity, `Example Asset`, defined as authbase `89cad9e3e34280eb1e8bc420542c00a7fcc01002b663dbf7f38bceddf80e680c` with a matching token category ID. `Example Asset` has the ticker symbol `XAMPL` and 6 decimal places, i.e. `1,000,000` fungible tokens should be displayed as `1.000000 XAMPL`.

The registry also includes some historical background for `Example Asset` – it was first released at `2023-01-03T00:00:00.000Z`, with the ticker symbol `EXAMPLE` and 8 decimal places before being redenominated and rebranded; from a user's perspective, `1 EXAMPLE` became `100 XAMPL`. The rebranding and re-denomination migration began at `2023-01-13T00:00:00.000Z` and was considered complete at `2023-02-13T00:00:00.000Z`. The old `icon` and a `web` URI providing more information about the migration is also included.

For more detail, see the [descriptions in the example](./examples/fungible-token.json).

## Art Collection

The [`art-collection.json` example](./examples/art-collection.json) demonstrates how the issuer of a non-fungible token (NFT) art collection might publish information about each token in the collection.

The registry includes only one identity, `Example NFT Collection`, defined as authbase `89cad9e3e34280eb1e8bc420542c00a7fcc01002b663dbf7f38bceddf80e680c` with a matching token category ID.

`Example NFT Collection` has the ticker symbol `XAMPLZ` and defines metadata for 3 sequential NFTs, `Example #0` (`XAMPLZ-0`), `Example #1` (`XAMPLZ-1`), and `Example #2` (`XAMPLZ-2`). The `icon` for each NFT is published via IPFS (as [recommended](./readme.md#publication-of-static-data)), so clients may download each icon by querying IPFS or by using [HTTP Gateways](https://docs.ipfs.tech/reference/http/gateway/), e.g. [`ipfs://bafybeihnmh5bkbaspp3xfdanje74pekhsklhobzzraeyywq6gcpb3iuvey/0.svg`](ipfs://bafybeihnmh5bkbaspp3xfdanje74pekhsklhobzzraeyywq6gcpb3iuvey/0.svg) may be accessed via CloudFlare's gateway at [`https://cf-ipfs.com/ipfs/bafybeihnmh5bkbaspp3xfdanje74pekhsklhobzzraeyywq6gcpb3iuvey/0.svg`](https://cf-ipfs.com/ipfs/bafybeihnmh5bkbaspp3xfdanje74pekhsklhobzzraeyywq6gcpb3iuvey/0.svg).

For more detail, see the [descriptions in the example](./examples/art-collection.json).

## Decentralized Application

The `decentralized-application.json` example demonstrates how a registry might specify the structure of NFTs used by a decentralized application.

The registry includes only one identity, `Crowdfunding Example`, defined as authbase `89cad9e3e34280eb1e8bc420542c00a7fcc01002b663dbf7f38bceddf80e680c` with a matching token category ID.

This decentralized application uses only one type of parsable NFT, `Pledge Receipt`, which itself contains only one field, `Pledge Value`. This field demonstrates the additional capabilities of the `number` encoding: clients are informed that `Pledge Value` can be aggregated (by addition) in views containing multiple NFTs to provide useful information to the user. For example, if the wallet holds two NFTs, one with a `Pledge Value` of `123456` and one of `654321`, the wallet can display a total of the user's pledges to this campaign in relevant user interfaces: `0.00777777 BCH`.

For more detail, see the [descriptions in the example](./examples/decentralized-application.json).
