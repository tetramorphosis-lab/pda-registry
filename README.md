# pda-registry — Black Hole package registry

Static index of `.s9pk` packages for StartOS, hosted on GitHub Releases.

The catalog is `index.json` at the root of this repo. Each package's
`s9pk` field is the URL of the release asset on this same repo.

## How operators use it

```bash
# inside the Black Hole stack
pda store install <package-name> <device>
```

`pda` reads `index.json`, downloads the `.s9pk` from its release URL,
verifies SHA256, and sideloads it onto your StartOS box.

## How operators add it to their StartOS marketplace

Browse Cloak's chat → "add this registry to my Black Hole" — Cloak
runs the marketplace.add RPC against your box, and the Black Hole
appears alongside Start9's official registry.

## Catalog

See `index.json` for the full list. Current packages: cloak, ollama,
i2pd, moneropay, ntfy, pairdrop, shadowsocks, tailscale.

## Building from source

The packaging code lives at <https://github.com/tetramorphosis-lab/peripheral-debug-agent/tree/main/packages>. Each package has its own `Makefile` that produces a `.s9pk`.

