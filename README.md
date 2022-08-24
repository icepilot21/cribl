# cribl
## Crible Docs:
- https://docs.cribl.io/stream/deploy-types/
- https://docs.cribl.io/stream

## Useful Cribl Stream CLI Commands:
### Service Management Commands
- Display a list of all available commands:
```
./cribl help -a
```
- Start Crible Stream Service
```
./cribl start
```
- Stop Crible Stream Service
```
./cribl stop
```
- Start Crible Stream Service
```
./cribl restart
```
- Check Cribl Status
```
./cribl status
```
- Enable boot start
```
./cribl boot-start <sub-command> <options> <args>
```
### Cribl Mode Commands
- Configure Cribl Edge as a single-instance deployment
```
./cribl mode-edge
```
- Configure Cribl Edge as an Edge Node
```
./cribl mode-managed-edge
```
- Configure Cribl Stream as a Leader Instance
```
cribl mode-master
```
- Configure Cribl Stream as a single-instance deployment
```
./cribl mode-single
```
- Configure Cribl Stream as a worker instance
```
./cribl mode-worker
```
### Manage Cribl Packs
- Manage Cribl Packs (Export, Install, List, Uninstall, and Upgrade)
```
./cribl pack <sub-command> <options> <args>
```
### Diagnostics
- Manage Disgnostic Bundles
```
./cribl diag <sub-command> <options> <args>
```
- Create Crible Stream Diagnostic Bundle in Debug Mode
```
./cribl diag create -d
```
- Send Cribl Stream Diagnostic Bundle to Cribl Support
```
./cribl diag send -c <Case Number>
```
- List Existing Cribl Stream/Edge Diagnostic Bundles
```
./cribl diag list
```
