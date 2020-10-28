# extract_from_text

Python functions to extract unstructured information from text.

## input:
string: the text to extract information from
or list of strings

## output:
json list of structured records

## Description
The function accepts a string or list of string and returns a list of structured records. The information is extracted using regex or python libraries. 


Extractors:



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





