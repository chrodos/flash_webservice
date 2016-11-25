# Flash Webservice

In this page you will find instructions on how to use the Web service for the FLASH reasoning engine. First you need to obtain an API key by sending an email to christos.rodosthenous at ouc dot ac dot cy. Then, you can call the api by accessing this address: http://cognition-srv1.ouc.ac.cy/smart_corpus_builder/ws2/api.php

Supported variables:
- api: The unique key assigned to you for using this webservice
- flash_rules: The Common Knowledge rules for flash in the form of text [*This variable is used with method flash_set_rules*]
- domain_id: The domain id that will be used to run a flash query [*This variable is used with method flash_run_query*]
- flash_query: The query in the form of text seperated by comma character (,) (e.g antarctica, funny, feathers)
- method: 
 - flash_set_rules: Stores the Common Knowledge rules for flash in the form of text and returns a domain_id
 - flash_run_query: Runs a query against the Common Knowledge rules stored previously in flash database(domain_id). It returns back a json string containing 3 properties (graph,trace,output):
  - graph: Includes all Common Knowledge rules that are activated
  - trace: The first element includes the query elements. The next elements are the rules and nodes activated.
  - output: Raw output of the prolog interpreter
 
 A complete example is presented in the file index.html using html5 and javascript (JQUERY Framework). Another example of using the webservice can be found in: http://cognition-srv1.ouc.ac.cy/flash_demo
 
 ## Flash_run_query output in JSON format
 ```
 {
	"graph": [{
		"rname": "rule4",
		"rbody": "feathers",
		"rnumeric": "0",
		"rhead": "bird"
	}, {
		"rname": "rule2",
		"rbody": "bird",
		"rnumeric": "0",
		"rhead": "flying"
	}, {
		"rname": "rule4",
		"rbody": "feathers",
		"rnumeric": "0",
		"rhead": "bird"
	}, {
		"rname": "rule5",
		"rbody": "(antarctica,bird,funny)",
		"rnumeric": "0",
		"rhead": "penguin"
	}, {
		"rname": "rule1",
		"rbody": "penguin",
		"rnumeric": "0",
		"rhead": "-flying"
	}, {
		"rname": "rule2",
		"rbody": "bird",
		"rnumeric": "0",
		"rhead": "flying"
	}, {
		"rname": "rule3",
		"rbody": "penguin",
		"rnumeric": "0",
		"rhead": "bird"
	}, {
		"rname": "rule4",
		"rbody": "feathers",
		"rnumeric": "0",
		"rhead": "bird"
	}, {
		"rname": "rule5",
		"rbody": "(antarctica,bird,funny)",
		"rnumeric": "0",
		"rhead": "penguin"
	}, {
		"rname": "rule6",
		"rbody": "flying",
		"rnumeric": "0",
		"rhead": "wings"
	}, {
		"rname": "rule1",
		"rbody": "penguin",
		"rnumeric": "0",
		"rhead": "-flying"
	}, {
		"rname": "rule2",
		"rbody": "bird",
		"rnumeric": "0",
		"rhead": "flying"
	}, {
		"rname": "rule3",
		"rbody": "penguin",
		"rnumeric": "0",
		"rhead": "bird"
	}, {
		"rname": "rule4",
		"rbody": "feathers",
		"rnumeric": "0",
		"rhead": "bird"
	}, {
		"rname": "rule5",
		"rbody": "(antarctica,bird,funny)",
		"rnumeric": "0",
		"rhead": "penguin"
	}, {
		"rname": "rule7",
		"rbody": "-flying",
		"rnumeric": "0",
		"rhead": "-feathers"
	}, {
		"rname": "rule1",
		"rbody": "penguin",
		"rnumeric": "0",
		"rhead": "-flying"
	}, {
		"rname": "rule2",
		"rbody": "bird",
		"rnumeric": "0",
		"rhead": "flying"
	}, {
		"rname": "rule3",
		"rbody": "penguin",
		"rnumeric": "0",
		"rhead": "bird"
	}, {
		"rname": "rule4",
		"rbody": "feathers",
		"rnumeric": "0",
		"rhead": "bird"
	}, {
		"rname": "rule5",
		"rbody": "(antarctica,bird,funny)",
		"rnumeric": "0",
		"rhead": "penguin"
	}, {
		"rname": "rule7",
		"rbody": "-flying",
		"rnumeric": "0",
		"rhead": "-feathers"
	}, {
		"rname": null,
		"rbody": null,
		"rnumeric": null,
		"rhead": null
	}],
	"trace": [{
		"values": ["antarctica", "funny", "feathers"]
	}, {
		"values": ["rule4"]
	}, {
		"values": ["bird"]
	}, {
		"values": ["rule2", "rule4", "rule5"]
	}, {
		"values": ["flying", "bird", "penguin"]
	}, {
		"values": ["rule1", "rule2", "rule3", "rule4", "rule5", "rule6"]
	}, {
		"values": ["-flying", "bird", "penguin", "wings"]
	}, {
		"values": ["rule1", "rule2", "rule3", "rule4", "rule5", "rule7"]
	}, {
		"values": ["-flying", "bird", "penguin"]
	}, {
		"values": ["rule1", "rule2", "rule3", "rule4", "rule5", "rule7"]
	}, {
		"values": ["-flying", "bird", "penguin"]
	}, {
		"values": []
	}],
	"output": ["%  utilities compiled 0.00 sec, 19 clauses", "%  syntax compiled 0.00 sec, 14 clauses", "%  cwpram compiled 0.00 sec, 7 clauses", "%  prune compiled 0.00 sec, 5 clauses", "%  reason compiled 0.00 sec, 25 clauses", "%  export compiled 0.00 sec, 6 clauses", "% \/var\/vhosts\/cognition-srv1\/smart_corpus_builder\/flash_reasoner\/engine_1132587085.pl compiled 0.01 sec, 101 clauses", "% .\/memory\/working\/rules_1132587085_472.pl compiled 0.00 sec, 9 clauses", "% .\/memory\/working\/query_968494303.pl compiled 0.00 sec, 2 clauses", "", ">>> perception: [antarctica,funny,feathers]", "", ">>> step: 1\/inf", " check: rule(rule1,penguin,0,-flying)", " check: rule(rule2,bird,0,flying)", " check: rule(rule3,penguin,0,bird)", " check: rule(rule4,feathers,0,bird)", "   infer: bird", " check: rule(rule5, (antarctica,bird,funny),0,penguin)", " check: rule(rule6,flying,0,wings)", " check: rule(rule7,-flying,0,-feathers)", "inferred: [rule4::bird]", "filtered: [rule4::bird]", "effected: [bird]", "", ">>> step: 2\/inf", " check: rule(rule1,penguin,0,-flying)", " check: rule(rule2,bird,0,flying)", "   infer: flying", " check: rule(rule3,penguin,0,bird)", " check: rule(rule4,feathers,0,bird)", "   infer: bird", " check: rule(rule5, (antarctica,bird,funny),0,penguin)", "   infer: penguin", " check: rule(rule6,flying,0,wings)", " check: rule(rule7,-flying,0,-feathers)", "inferred: [rule2::flying,rule4::bird,rule5::penguin]", "filtered: [rule2::flying,rule4::bird,rule5::penguin]", "effected: [flying,bird,penguin]", "", ">>> step: 3\/inf", " check: rule(rule1,penguin,0,-flying)", "   infer: -flying", " check: rule(rule2,bird,0,flying)", "   infer: flying", " check: rule(rule3,penguin,0,bird)", "   infer: bird", " check: rule(rule4,feathers,0,bird)", "   infer: bird", " check: rule(rule5, (antarctica,bird,funny),0,penguin)", "   infer: penguin", " check: rule(rule6,flying,0,wings)", "   infer: wings", " check: rule(rule7,-flying,0,-feathers)", "inferred: [rule1:: -flying,rule2::flying,rule3::bird,rule4::bird,rule5::penguin,rule6::wings]", "filtered: [rule1:: -flying,rule2::flying,rule3::bird,rule4::bird,rule5::penguin,rule6::wings]", "effected: [-flying,bird,penguin,wings]", "", ">>> step: 4\/inf", " check: rule(rule1,penguin,0,-flying)", "   infer: -flying", " check: rule(rule2,bird,0,flying)", "   infer: flying", " check: rule(rule3,penguin,0,bird)", "   infer: bird", " check: rule(rule4,feathers,0,bird)", "   infer: bird", " check: rule(rule5, (antarctica,bird,funny),0,penguin)", "   infer: penguin", " check: rule(rule6,flying,0,wings)", " check: rule(rule7,-flying,0,-feathers)", "   infer: -feathers", "inferred: [rule1:: -flying,rule2::flying,rule3::bird,rule4::bird,rule5::penguin,rule7:: -feathers]", "filtered: [rule1:: -flying,rule2::flying,rule3::bird,rule4::bird,rule5::penguin,rule7:: -feathers]", "effected: [-flying,bird,penguin]", "", ">>> step: 5\/inf", " check: rule(rule1,penguin,0,-flying)", "   infer: -flying", " check: rule(rule2,bird,0,flying)", "   infer: flying", " check: rule(rule3,penguin,0,bird)", "   infer: bird", " check: rule(rule4,feathers,0,bird)", "   infer: bird", " check: rule(rule5, (antarctica,bird,funny),0,penguin)", "   infer: penguin", " check: rule(rule6,flying,0,wings)", " check: rule(rule7,-flying,0,-feathers)", "   infer: -feathers", "inferred: [rule1:: -flying,rule2::flying,rule3::bird,rule4::bird,rule5::penguin,rule7:: -feathers]", "filtered: [rule1:: -flying,rule2::flying,rule3::bird,rule4::bird,rule5::penguin,rule7:: -feathers]", "effected: [-flying,bird,penguin]", "", ">>> frontier size = 1", ">>> conclusion: [antarctica,funny,feathers,bird,penguin,-flying]", ""]
}
 ```

## Code example for storing Common Knowledge rules (using jquery framework):
```
$.ajax({
            type: 'POST',
            url: 'http://cognition-srv1.ouc.ac.cy/smart_corpus_builder/ws2/api.php',
            data: {
                'api': '54606e96f52a13e5d2f2258c637d8e98',
                'method': 'flash_set_rules',
                'flash_rules': 'rule1 :: penguin implies -flying.'
            },
                         success: function (data) {
                            alert('Domain ID: '+data);
                         }
			 });
```
## Code example for querying the Common Knowledge rules database (using jquery framework):
```
$.ajax({
            type: 'POST',
            url: 'http://cognition-srv1.ouc.ac.cy/smart_corpus_builder/ws2/api.php',
            data: {
                'api': '54606e96f52a13e5d2f2258c637d8e98',
                'method': 'flash_run_query',
		'domain_id':'2',
                'flash_query': 'antarctica, funny, feathers'
            },
                         success: function (data) {
                            alert('Domain ID: '+data);
                         }
			 });
```
**Note**: The api keys used in these examples are for demo purposes only (not working). You must obtain a unique api key to use this webservice.
