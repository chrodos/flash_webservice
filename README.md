# Flash Webservice
In this page you will find instructions on how to use the Web service for the FLASH reasoning engine

First you need to obtain an API key by sending an email to christos.rodosthenous at ouc dot ac dot cy

Then, you can call the api by accessing this address: http://cognition-srv1.ouc.ac.cy/smart_corpus_builder/ws2/api.php

Supported variables:
- api: The unique key assigned to you for using this webservice
- flash_rules: The Common Knowledge rules for flash in the form of text
- method: 
 - flash_set_rules: Stores the Common Knowledge rules for flash in the form of text and returns a domain_id
 - flash_run_query: Runs a query by using

example (using jquery):
http://cognition-srv1.ouc.ac.cy/smart_corpus_builder/ws2/api.php?api=1234567890&method=
2) flash_run_query: Runs a query by using

