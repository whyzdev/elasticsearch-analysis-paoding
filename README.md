Paoding Analysis for ElasticSearch
==================================

The Paoding Analysis plugin integrates Paoding(http://code.google.com/p/paoding/) module into elasticsearch.

In order to install the plugin, simply run: `bin/plugin -install thihy/elasticsearch-analysis-paoding`.

    --------------------------------------------------
    | Paoding    Analysis Plugin    | ElasticSearch  |
    --------------------------------------------------
    | master                        | master         |
    --------------------------------------------------
    | 1.4.1.0                       | 1.4.x          |
    --------------------------------------------------

The plugin includes `paoding` analyzer and `paoding` tokenizer.

optional config `mode` can be set to `most_tokens` or `max_length`

1.install the paoding analysis plugin

2.create a index with paoding analysis config

```
curl -XPUT http://localhost:9200/thihy/ -d'
{
   "index":{
      "analysis":{
         "analyzer":{
            "paoding_1":{
               "type":"paoding",
               "mode":"max_length",
               "dict":{
               	"type":"file",
               	"file":{
               		"dir":"／path/to/dir"
               	}
               }
            }
         }
      }
   }
}'
```
