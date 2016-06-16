# Steam Workshop Content Downloader
Little script for downloading plugins from steam workshop for server that do not
support natively the workshop like left4dead2 server.

## How to use
Download the script and run it with the plugin(s) id or collection id as arg. Note that it
will also download the content of the linked collection.

## Usage
### Command
```bash
./workshop.py [-o <output_dir>] [-c <collection_id>]... [-d <plugin_id>]... [<plugin_id>]... <plugin_id>
```

### Add plugins
Run the script with as many plugin_id as you want
```bash
./workshop.py <plugin_1_id> <plugin_2_id> ... <plugin_n_id>
```

### Add collections
```bash
./workshop.py -c <conllection_1_id> -c <conllection_2_id> ... -c <conllection_n_id>
```

### Update plugins
Just run the script
```bash
./workshop.py
```
Note that each time the script is call, the plugins will be updated if needed.
If you already have the plugins download, the script will redownload everything
the first time.

### Remove plugins
```bash
./workshop.py -d <plugin_1_id> -d <plugin_2_id> ... -d <plugin_n_id>
```
You still need to remove manually the plugin (.zip) file.

## Save file
The save file name addons.lst is write in json and has the following form :
```json
{
    "plugins": {
        "<plugin_1_id>": {
            "title": "Title of the plugin",
            "time_updated": <last_updated_time_unix_timestamp>
        },
        "<plugin_2_id>": {
            "title": "Title of the plugin",
            "time_updated": <last_updated_time_unix_timestamp>
        },
        ...
        "<plugin_n_id>": {
            "title": "Title of the plugin",
            "time_updated": <last_updated_time_unix_timestamp>
        }
    }
}
```
This file is generated the first time you run the script with the plugin(s) id
or a collection id.

## Example
### First run
```bash
./workshop.py -o /path/to/l4d2/addons/workshop 121086524
```

### Add new collection
```bash
./workshop.py -o /path/to/l4d2/addons/workshop -c 313949718
```
Will download all plugins from 313949718 collection

### Update all plugins
```bash
./workshop.py
```

# Tags
steam workshop plugin collection download
