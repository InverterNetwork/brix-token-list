# Brix Token List

Ethereum mainnet emUSD, wemUSD, iTRY, and wiTRY metadata for CoW Swap and compatible token-list consumers. No testnet or bridged tokens are included.

## Integration URL

Public token-list URL:

https://raw.githubusercontent.com/InverterNetwork/brix-token-list/main/tokenlist.json

CoW must add the list to its interface; hosting alone does not list the tokens or enable trading.

## Verified token metadata

All four tokens are on Ethereum mainnet (chain ID 1).

| Symbol | Name | Address | Decimals |
|---|---|---|---|
| emUSD | emUSD | `0x61a075979fD5D9fC3B4f3db8aC77B710B03EcDc2` | 18 |
| wemUSD | wemUSD | `0xefE3c772C7020F14d5f6b9d7436f1b8Dfa8fB5AF` | 18 |
| iTRY | iTRY | `0xb492B4aFD9658093694CF9452D5C272e8230F3B0` | 18 |
| wiTRY | Wrapped iTRY | `0xE346C29b5B60Ef870b9724c57ccfbBc631e47DEE` | 18 |

The emUSD and wemUSD metadata was read directly from Ethereum mainnet at block **26147019** on 8 October 2026. Both addresses match issuer production configuration, and wemUSD’s `asset()` returned the emUSD address. Verification required no transaction or signature.

The iTRY and wiTRY addresses match the [Brix Ethereum deployment documentation](https://docs.brix.money/resources/contracts). The list uses Brix’s public token labels.

## Assets

`logos/emusd.svg` and `logos/wemusd.svg` are the original frontend token icons supplied by the design team, copied without modification from `packages/web-consumer/public/tokens/` at frontend commit `9c18bb1b72717b0405c82576b7ae84316199bb20`.

The SVGs include Figma-generated HTML `foreignObject` conic gradients. Their markup contains no scripts or external references. Check rendering in CoW's image component before activation; if its image pipeline strips those gradients, request flat PNG exports from design. No substitute artwork is used.

The iTRY and wiTRY logo URLs point to the token icons on the official Brix website.

## Validation and maintenance

The initial list passes the official Uniswap Token Lists draft-07 JSON schema, including URI and timestamp formats. Token addresses are checksummed; symbols, names and decimals were verified on-chain.

Schema: https://github.com/Uniswap/token-lists/blob/main/src/tokenlist.schema.json

For updates, verify new metadata on the intended chain, update the timestamp and version, and validate before publishing. Increment major for removed tokens/address changes, minor for added tokens, and patch for metadata corrections. Keep logo URLs publicly accessible without authentication.

## CoW integration

Share the raw token-list URL above with CoW for inclusion. Verify logo rendering in their image component. Adding the list does not activate solver routes or grant any contract permissions.

Future issuer assets can be added after their chain, metadata and official artwork are verified.
