# Voidstone-Data

Voidstone-Data is a public repository containing Minecraft UUIDs and Discord user IDs linked to their respective accounts.

It serves as a shared source of account-linking data for Voidstone mods and other projects that need to identify linked Minecraft and Discord accounts.

## Repository Structure

```text
Voidstone-Data/
├── README.md
├── schema.json
└── players/
    ├── PlayerName.json
    └── ...
```

## Player Records

Each file in `players/` represents one linked player.

The filename is for human reference only. It can be any descriptive name and does not determine the player's identity.

Example: `players/PlayerName.json`

```json
{
  "minecraft_uuid": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "discord_uid": "123456789012345678"
}
```

### Fields

| Field | Description |
|---|---|
| `minecraft_uuid` | The player's Minecraft account UUID. |
| `discord_uid` | The player's Discord user ID. |

Both values are stored as strings.

## Schema

`schema.json` defines the expected structure and validation rules for player records.

Every player record must contain both `minecraft_uuid` and `discord_uid`. No additional fields are part of the record format.

## Usage

Projects can retrieve player records directly from this public GitHub repository.

A project can:

1. Retrieve the list of files in the `players/` directory.
2. Fetch and parse the JSON files.
3. Compare `minecraft_uuid` against a Minecraft player's UUID.
4. Read the corresponding `discord_uid` when a matching record is found.

Projects should cache retrieved records and refresh them as appropriate rather than repeatedly downloading every file.

## Data Scope

Voidstone-Data stores only Minecraft UUIDs and Discord user IDs.

It does not store permissions, roles, player statistics, inventory data, item ownership, or other gameplay information.

## Contributing

Player records should follow the format defined in `schema.json`. When adding or updating a record, ensure that both IDs are correct and that the JSON is valid.

---

Maintained by [BlueGamerwolf](https://github.com/BlueGamerwolf).