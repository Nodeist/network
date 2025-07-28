# How to create a gentx

This document describes how to create a gentx (genesis transaction).
Use `sunrised` binary for the Mainnet.
<https://github.com/sunriselayer/sunrise/releases/tag/v1.0.0>

Please use `genesis.json` in this directory, and submit it to the `validators` directory.

## Command

```bash
sunrised genesis gentx [validator-key-name] [amount] --home [path-to-home-directory] --chain-id [chain-id] --moniker [your-moniker] --details "[your-details]" --website [your-website] --identity [your-identity] --security-contact [your-security-contact]
```

## Parameters

> [!NOTE]
>
> - `[amount]`: Please be sure to use `1000000uvrise` (1 vRISE).
> - `--chain-id`: Please be sure to use `sunrise-1`.

| Parameter                      | Description                                                                | Example                   |
| ------------------------------ | -------------------------------------------------------------------------- | ------------------------- |
| `[validator-key-name]`         | The name of the validator key.                                             | `$VAL1`                   |
| `[amount]`                     | The amount of tokens to stake. USE `uvrise` (vRISE)                        | `1000000uvrise`           |
| `--home`                       | The path to the home directory of your node.                               | `$NODE_HOME`              |
| `--chain-id`                   | The chain ID. USE `sunrise-1`                                              | `sunrise-1`               |
| `--moniker`                    | The moniker of the node. This is a human-readable name for your validator. | `sunrise-dev`             |
| `--details`                    | A description of your validator.                                           | `"sample for gentx"`      |
| `--website`                    | The website of your validator.                                             | `https://sunriselayer.io` |
| `--identity`                   | The identity of your validator. (e.g. Keybase)                             | `6A87A19E54244E34`        |
| `--security-contact`           | The security contact of your validator.                                    | `contact@sunriselayer.io` |
| `--commission-rate`            | The commission rate of your validator.                                     | `0.1`                     |
| `--commission-max-rate`        | The maximum commission rate of your validator.                             | `0.2`                     |
| `--commission-max-change-rate` | The maximum change rate of your validator.                                 | `0.01`                    |

## Example

Here is an example of the command.

```bash
sunrised genesis gentx $VAL 1000000uvrise --home $NODE_HOME --chain-id sunrise-1 --moniker sunrise-dev --details "sample for gentx" --website https://sunriselayer.io --identity 6A87A19E54244E34 --security-contact contact@sunriselayer.io --commission-rate 0.1 --commission-max-rate 0.20 --commission-max-change-rate 0.01
```

## Success Response

If the command is successful, you will see a response like this:

```
Genesis transaction written to "sunrise/config/gentx/gentx-baee32256a6b9d95b00664689f067454fe0b07be.json"
```

## Verify your gentx

```bash
sunrised genesis collect-gentxs
```

## Genesis File

The `genesis.json` file in this directory is for creating gentx. It will be replaced at the start of the mainnet.
