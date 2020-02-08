# catalyst-snapshots
Official snapshot of Catalyst DB for bootstrapping

Steps:
- download the snapshot from here https://storage.googleapis.com/cx-snapshot-height-366230/cx-snapshot-height-366230.zip, on linux simply use ` wget <link_to_snapshot>` to download the zip
- unzip the folder
- make sure Catalystd is not running on your machine
- remove the database files, for linux this would be `rm -r .Catalyst/`
- copy the contents of the zip into `.Catalyst/`, and restart `Catalystd`, it will use the snapshot to reconstruct the Blockchain
- If your node appears to be doing nothing on restart, it is likely due to the outdated p2pstate.bin - give the node 10-15 minutes if it does not begin to sync new blocks stop it and run `rm .Catalyst/p2pstate.bin` then start your node again and it should begin syncing normally.
