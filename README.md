# extract_from_html

Python functions to extract unstructured information from html.

## Requirements
- Develop extractors to retrieve each of the following information from a html string:
  - text
  - links
  - rss feeds
  - domain
  - google analytics id
  - sctuctured data / microdata
  - 


- Output result in a list of json-ld schema.org records
  - email: https://schema.org/ContactPoint 
  - phone: https://schema.org/ContactPoint
  - url: https://schema.org/WebPage
- Develop test cases for each extractors that includes the following scenarios:
  - Valid, typical input
  - Null input
  - Non-string input
  - Non-existing object in string (for example, testing the phone extractor and no phone number is in the test input string).
  - Multiple object in string
  

## input:
string: the text to extract information from
or list of strings

## output:
json list of structured records

## Description
The function accepts a string or list of string and returns a list of structured records. The information is extracted using regex or python libraries. 

Each record contains a reference to the extractor that has been used. 
For example, the string "Steve can be reached at steve@apple.com" would give:
```
    {
    "@type": schema:contactpoint",
    "schema:email": "steve@apple.com",
    "kraken:extractor": "extract_from_text-email_extractor",
    "kraken:extracteddate": 2020-10-28T20:43:55+00:00
    }
```

## Extractors:

Object extracted | Extractor name | Library
-----------------|----------------|--------
Emails | email_extractor_regex | regex
URLs | url_extractor_ioc-finder | ioc-finder
URLs | url_extractor_regex | regex
Phone numbers | phone_extractor_ioc_finder | ioc-finder
City, state, country | geo_extractor_geograpy3 | geograpy3
Job title | title_extractor |
Quantities | qty_extractor_quantulum3 | quantulum3






