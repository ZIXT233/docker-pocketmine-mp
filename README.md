docker-pocketmine-mp
====================

Docker image for a PocketMine-MP server.
Since it includes the latest stable version of PocketMine-MP that is not working with the latest Minecraft PE, you should update to the latest beta. Check "Update Beta" section.

**For the moment, installing beta release instead of stable one by default.**

Quick Start
--------------------

```
docker run --name=pocketmine-mp -d -p 19132:19132/udp 5t111111/pocketmine-mp:latest
```

Data Persistence
--------------------

You might want to keep your data from losing. The easiest way is to create a direcory on host filesystem and mount it to `/pocketmine/PocketMine-MP` in a container.  

For example, this instruction shows in case of you want to use host's `/opt/pocketmine-mp` directory for saving your data.

```
mkdir /opt/pocketmine-mp
```

Then run a container with `-v` option.

```
docker run --name=pocketmine-mp -d -v /opt/pocketmine-mp:/pocketmine/PocketMine-MP \
    -p 19132:19132/udp 5t111111/pocketmine-mp:latest
```

You can also edit `server.properties`. 

Update
--------------------

Set the environment variable `UPDATE_LATEST = YES` to force update the latest stable release.

```
docker run --name=pocketmine-mp -d -v /opt/pocketmine-mp:/pocketmine/PocketMine-MP \
    -p 19132:19132/udp -e "UPDATE_LATEST=YES" 5t111111/pocketmine-mp:latest
```

Update Beta
--------------------

Set the environment variable `UPDATE_LATEST_BETA = YES` to force update the latest beta release.

```
docker run --name=pocketmine-mp -d -v /opt/pocketmine-mp:/pocketmine/PocketMine-MP \
    -p 19132:19132/udp -e "UPDATE_LATEST_BETA=YES" 5t111111/pocketmine-mp:latest
```


Update Dev
--------------------

Set the environment variable `UPDATE_LATEST_DEV = YES` to force update the latest development release.

```
docker run --name=pocketmine-mp -d -v /opt/pocketmine-mp:/pocketmine/PocketMine-MP \
    -p 19132:19132/udp -e "UPDATE_LATEST_DEV=YES" 5t111111/pocketmine-mp:latest
```
