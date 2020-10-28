# extract_from_text

Python functions to extract unstructured information from text.

## Requirements
- Develop extractors to retrieve each of the following information from a string:
  - Emails
  - URLs
  - Phone numbers (https://pypi.org/project/ioc-finder/)
  - Cities, states / provinces, countries (geograpy3)
  - Job titles (find-job-titles)
  - Quantities (quantulum3)
- Normalize the data found
  - Phone number: E.164
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
{"@type": schema:contactpoint",
"schema:email": "steve@apple.com",
"kraken:extractor": "extract_from_text-email_extractor"
}


Extractors:

Object extracted | Extractor name | Library
-----------------|----------------|--------
Emails | email_extractor | regex
URLs | url_extractor | ioc-finder
URLs | url_extractor | regex
Phone numbers | phone_extractor | ioc-finder
City, state, country | geo_extractor | geograpy3
Job title | title_extractor |
Quantities | qty_extractor | quantulum3




## Test cases:
### 1. Null
input:
null value

output:
[] (empty list)

### 2. Non string
input:
nons-string value (byte, etc).

output:
[] (empty list)

### 3. String
input: 'Steve Jobs works for aple and can be reached at 514 555-3321. he lives in Montreal, Qc. His email is steve@apple.com.'
string

output:
{
"@type": "schema:person",
"schema:givenname": "Steve",
"schema:familyname": "Jobs"
},





