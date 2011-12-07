var fs       = require('fs'),
    date     = require('../lib/dateutil').format,
    assert   = require('assert');

// Read test data
var testDataFile  = fs.readFileSync(__dirname + '/testdata', 'utf8');
var testDataLines = testDataFile.split('\n');
var testData = [];
for(var t in testDataLines) {
	// *     example 1: date('H:m:s \\m \\i\\s \\m\\o\\n\\t\\h', 1062402400);
	// *     returns 1: '09:09:40 m is month'
	var matches = testDataLines[t].match(/^\/\/ \*     (\w+) (\d+):\s*'?(.*?)'?$/);
	if(matches) {
		var type   = matches[1];
		var number = matches[2];
		var data   = matches[3];
		
		if(null == testData[number])
			testData[number] = { example : [], returns : null };
		
		if('example' == type) {
			testData[number][type].push(data);
		} else {
			testData[number][type] = data;
		}
	}
}

// Run the tests
for(var t in testData) {
	var evalStrings = testData[t].example;
	var resultStr   = testData[t].returns;
	
	var result;
	for(var e in evalStrings) {
		result = eval(evalStrings[e]).toString();
	};
	
	console.log("Testing #%d : %s", t, result == resultStr ? 'passed' : 'failed! (' + result + ' != ' + resultStr + ')');
}