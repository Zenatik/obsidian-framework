# YouTube
```json
{
	"schemaVersion": "0.1.0",
	"name": "YouTube",
	"behavior": "create",
	"noteNameFormat": "{{schema:author}} – {{schema:name}}",
	"path": "Clippings",
	"noteContentFormat": "![{{schema:name}}]({{url}})",
	"properties": [
		{
			"name": "title",
			"value": "{{schema:name}}",
			"type": "text"
		},
		{
			"name": "author",
			"value": "{{schema:author|wikilink}}",
			"type": "multitext"
		},
		{
			"name": "published",
			"value": "{{schema:uploadDate|date:YYYY-MM-DD}}",
			"type": "date"
		},
		{
			"name": "url",
			"value": "{{url}}",
			"type": "text"
		},
		{
			"name": "image",
			"value": "{{schema:thumbnailUrl|slice:0}}",
			"type": "text"
		},
		{
			"name": "created",
			"value": "{{date:YYYY-MM-DD}}",
			"type": "text"
		},
		{
			"name": "tags",
			"value": "resource/videos",
			"type": "text"
		}
	],
	"triggers": [
		"https://www.youtube.com/watch?v="
	]
}
```

# Google Maps
```json
{
	"schemaVersion": "0.1.0",
	"name": "Google Maps",
	"behavior": "create",
	"noteNameFormat": "{{selector:div[role=\"main\"]:aria-label}}",
	"path": "References",
	"noteContentFormat": "",
	"properties": [
		{
			"name": "type",
			"value": "",
			"type": "multitext"
		},
		{
			"name": "source",
			"value": "{{url}}",
			"type": "text"
		},
		{
			"name": "loc",
			"value": "",
			"type": "multitext"
		},
		{
			"name": "location",
			"value": "{{url|split:\\\"/@\\\"|slice:1|split:\\\",\\\"|slice:0,2}}",
			"type": "multitext"
		},
		{
			"name": "address",
			"value": "{{selector:button[aria-label^=\\\"Address:\\\"]:aria-label|split:\\\"Address: \\\"|slice:1}}",
			"type": "text"
		},
		{
			"name": "url",
			"value": "{{selector:div[aria-label^=\\\"Information for\\\"] a[href*=\\\"http\\\"]:href|slice:0,1}}",
			"type": "text"
		},
		{
			"name": "rating",
			"value": "",
			"type": "number"
		},
		{
			"name": "scoreGoogle",
			"value": "{{selector:div[jsaction*=\\\"moreReviews\\\"] .fontDisplayLarge}}",
			"type": "number"
		},
		{
			"name": "description",
			"value": "{{selector:div[aria-label^=\\\"About \\\"] button .PYvSYb[jslog]}}",
			"type": "text"
		},
		{
			"name": "created",
			"value": "{{date:YYYY-MM-DD}}",
			"type": "date"
		},
		{
			"name": "last",
			"value": "{{date:YYYY-MM-DD}}",
			"type": "date"
		},
		{
			"name": "tags",
			"value": "resource/places",
			"type": "multitext"
		}
	],
	"triggers": [
		"https://www.google.com/maps/place/"
	]
}
```

# IMDB
```json
{
	"schemaVersion": "0.1.0",
	"name": "IMDB",
	"behavior": "create",
	"noteNameFormat": "{{schema:name}}",
	"path": "References",
	"noteContentFormat": "",
	"properties": [
		{
			"name": "categories",
			"value": "[[Movies]]",
			"type": "multitext"
		},
		{
			"name": "genre",
			"value": "{{schema:genre|wikilink|join}}",
			"type": "multitext"
		},
		{
			"name": "director",
			"value": "{{schema:director[*].name|wikilink|join}}",
			"type": "multitext"
		},
		{
			"name": "rating",
			"value": "",
			"type": "number"
		},
		{
			"name": "scoreImdb",
			"value": "{{schema:aggregateRating.ratingValue}}",
			"type": "number"
		},
		{
			"name": "cast",
			"value": "{{schema:actor[*].name|slice:0,5|wikilink|join}}",
			"type": "multitext"
		},
		{
			"name": "cover",
			"value": "{{schema:image}}",
			"type": "text"
		},
		{
			"name": "plot",
			"value": "{{schema:description}}",
			"type": "text"
		},
		{
			"name": "year",
			"value": "{{schema:datePublished|split:\\\"-\\\"|slice:0,1}}",
			"type": "number"
		},
		{
			"name": "created",
			"value": "{{date:YYYY-MM-DD}}",
			"type": "date"
		},
		{
			"name": "tags",
			"value": "resource/movies",
			"type": "multitext"
		}
	],
	"triggers": [
		"/^https:\\/\\/www\\.imdb\\.com\\/title\\/tt\\d+(?!\\/reference\\/)(\\/[^\\s]*)?$/"
	]
}
```

# Product
```json
{
	"schemaVersion": "0.1.0",
	"name": "Product",
	"behavior": "create",
	"noteNameFormat": "{{title}}",
	"path": "References",
	"noteContentFormat": "{{description}}",
	"properties": [
		{
			"name": "created",
			"value": "{{date:YYYY-MM-DD}}",
			"type": "date"
		},
		{
			"name": "description",
			"value": "{{description}}",
			"type": "text"
		},
		{
			"name": "url",
			"value": "{{url}}",
			"type": "text"
		},
		{
			"name": "title",
			"value": "{{schema:@Product:name}}",
			"type": "text"
		},
		{
			"name": "price",
			"value": "{{meta:property:product:price:amount}}",
			"type": "number"
		},
		{
			"name": "image",
			"value": "{{image}}",
			"type": "text"
		},
		{
			"name": "tags",
			"value": "resource/products",
			"type": "text"
		}
	],
	"triggers": [
		"schema:@Product"
	]
}
```
# TWiT Podcast
```json
{
	"schemaVersion": "0.1.0",
	"name": "TWiT Podcast",
	"behavior": "create",
	"noteContentFormat": "{{content}}",
	"properties": [
		{
			"name": "tags",
			"value": "resource/podcasts, resource/podcast-episodes",
			"type": "multitext"
		},
		{
			"name": "podcast",
			"value": "[[This Week in Tech]]",
			"type": "text"
		},
		{
			"name": "url",
			"value": "{{url}}",
			"type": "text"
		},
		{
			"name": "hosts",
			"value": "{{\\\"create a comma delimited list of Guests\\\"}}",
			"type": "multitext"
		},
		{
			"name": "rating",
			"value": "",
			"type": "number"
		},
		{
			"name": "created",
			"value": "{{date:YYYY-MM-DD}}",
			"type": "date"
		}
	],
	"triggers": [
		"https://twit.tv/shows/"
	],
	"noteNameFormat": "{{meta:property:og:title}}",
	"path": "References"
}
```

# Good Reads
```json
{
	"schemaVersion": "0.1.0",
	"name": "Goodreads",
	"behavior": "create",
	"noteContentFormat": "## Summary\n\n{{selector:.BookPageMetadataSection__description}}\n\n\n## Cover\n![cover]({{image}})\n",
	"properties": [
		{
			"name": "tags",
			"value": "resource/books",
			"type": "multitext"
		},
		{
			"name": "author",
			"value": "{{author|wikilink|join}}",
			"type": "multitext"
		},
		{
			"name": "genre",
			"value": "{{\\\"generate a comma delimited list of the genre's this book is part of\\\"}}",
			"type": "text"
		},
		{
			"name": "pages",
			"value": "{{schema:numberOfPages}}",
			"type": "number"
		},
		{
			"name": "isbn",
			"value": "{{schema:isbn}}",
			"type": "text"
		},
		{
			"name": "cover",
			"value": "{{schema:image}}",
			"type": "text"
		},
		{
			"name": "url",
			"value": "{{url}}",
			"type": "text"
		},
		{
			"name": "rating",
			"value": "",
			"type": "number"
		},
		{
			"name": "created",
			"value": "{{date:YYYY-MM-DD}}",
			"type": "date"
		}
	],
	"triggers": [
		"https://www.goodreads.com/book/"
	],
	"noteNameFormat": "{{schema:name}}",
	"path": "References"
}
```