# RDX Addonaccount
Addonaccount System for RedM Extended

## Requirements
- [RedM Extended](https://github.com/ThymonA/redm_extended)

## How to install
* Download the lastest version of RDX Addonaccount
* Copy and paste ```rdx_addonaccount``` folder to ```resources/rdx_addonaccount```
* Insert the .sql file into your database.
* Add ```ensure rdx_addonaccount``` to your ```server.cfg``` file
* Now you are ready!

## Usage
There is two types of accounts: shared and not shared.

- Shared accounts doesn't belong to a specific user. Example: society accounts.
- None-shared accounts are created for every user in the server. They are created in db when player is loaded, Example: property black money

### `addon_account` database information
An addon account must be configured in the database before using it. Don't forget to run a server restart afterwards (you can alternative restart the script and relog all clients)

| `name`   | `label` | `shared` |
| -------- | ------- | -------- |
| name of the account | label of the account (not used) | is the account shared with others? (boolean either `0` or `1`) |

```lua
TriggerEvent('rdx_addonaccount:getSharedAccount', 'society_realestateagent', function(account)
	account.addMoney(500)
end)

TriggerEvent('rdx_addonaccount:getAccount', 'property_black_money', 'steam:0123456789', function(account)
	account.removeMoney(500)
end)
```
