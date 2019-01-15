# Munin plugins

## Reference source
[Munin plugins for MongoDB](https://github.com/comerford/mongo-munin)

## Plugins
- mongo_collections: collection count.

## Requirements
- MongoDB 4
- python/pymongo 3.\*

## Install Plugins
```
git clone https://github.com/remu1519/mongo-munin.git
sudo ln -sf /usr/share/munin/plugins/mongo_collections /etc/munin/plugins/mongo_collections
sudo chmod +x /usr/share/munin/plugins/mongo_collections
sudo systemctl restart munin-node
```

Check if plugins are running:
```
munin-node-configure | grep mongo_collections
```

Test plugin output:
```
munin-run mongo_collections
```

## Configuration

### how to configure custom db connection

munin-node can set env value in below file:
`/etc/munin/plugin-conf.d/munin-node`

```
[mongo_*]
env.MONGO_DB_URI mongodb://user:password@host:port/dbname
env.MONGO_DB_COLLECTION dbname
```
