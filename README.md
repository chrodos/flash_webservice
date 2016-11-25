# Flash Webservice
In this page you will find instructions on how to use the Web service for the FLASH reasoning engine

First you need to obtain an API key by sending an email to christos.rodosthenous at ouc dot ac dot cy

Then, you can call the api by accessing this address: http://cognition-srv1.ouc.ac.cy/smart_corpus_builder/ws2/api.php

Supported variables:
- api: The unique key assigned to you for using this webservice
- flash_rules: The Common Knowledge rules for flash in the form of text [*This variable is used with method flash_set_rules*]
- domain_id: The domain id that will be used to run a flash query [*This variable is used with method flash_run_query*]
- flash_query: The query in the form of text
- method: 
 - flash_set_rules: Stores the Common Knowledge rules for flash in the form of text and returns a domain_id
 - flash_run_query: Runs a query against the Common Knowledge rules stored previously in flash database(domain_id)

example (using jquery):
```
$.ajax({
            type: 'GET',
            url: 'http://cognition-srv1.ouc.ac.cy/smart_corpus_builder/ws2/api.php',
            data: {
                'api': '54606e96f52a19e5d2f2258c637d8e98',
                'method': 'flash_set_rules',
                'flash_rules': 'rule1 :: penguin implies -flying.'

            },
                         beforeSend: function () {
							//alert($("#rules_flash").val());
							//var allthedomain = $("#rules_flash").val();
							var allthedomain = $("#rules_flash").val();
							//alert(allthedomain);
							document.getElementById('graphhere').id = 'cy';
							```

