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
## Configuring Splunk as a Stream Source
- Type: Push
- TLS Support: Yes
- Event Breaker Support: Yes
- Splunk TCP Source is pre-configured to listen on port 9997
- Persistent Queue Settings: Default is NO
  - When toggled to YES, you need to set the mode condition:
    - Smart (only engages persitent queueing when it detects backpressure from the data processing engine)
    - Always On (will always write events into persistent queueing, prior to forwarding to the data processing engine)
### Configuring a SUF
- You need to specify the Cribl Workers as destinations (in outputs.conf)
- EXAMPLE:
```
[tcpout]
disabled = false
defaultGroup = cribl, <optional_clone_target_group>,

[tcpout:cribl]
server = [<cribl_ip>|<cribl_host>]:<port>, [<cribl_ip>|<cribl_host>]:<port>, ...
sendCookedData=true
```
- Next (in Stream GUI), configure a Splunk source
  - Ensure that you are listening on the correct port
![image](https://user-images.githubusercontent.com/35534434/186501296-b6881add-670d-4ecb-a407-8b8d88e0d534.png)
- Configuring Splunk SUF to send data to Indexer using Splunk default certs
![image](https://user-images.githubusercontent.com/35534434/186501786-ce5abf08-4234-42ea-8171-93b0d1ab670c.png)
- Configuring SUF to send data to Cribl Stream, then to Indexer using Splunk default certs
![image](https://user-images.githubusercontent.com/35534434/186502349-31e39f5c-ba8e-4bbf-b5b5-9bd18a85d057.png)
