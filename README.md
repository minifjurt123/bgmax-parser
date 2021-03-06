# bgmax-parser

## A Javascript Parser for Bg Max

### Description
A Parser that reads a string from a Bg Max file with Javascript.

### Example Usage
```js
const fs = require('fs');
const parser = require('bgmax-parser');

let pathToFile = './node_modules/bgmax-parser/example-files/bankgiroinbetalningar_exempelfil_avtal-om-ocr-kontroll_checksiffra_langd_sv.txt'
const content = fs.readFileSync(pathToFile, 'latin1'); // Bankgiro uses latin1 encoding
const parsedBgMax = parser(content);
console.log(parsedBgMax)
```

### Example Output
The example usage above will transform the Bg Max text file to a Javascript Array that looks like this:
<details>
  <summary>Click to show example output Array</summary>

```js
[
	{
		"transactionCode": "01",
		"entryDefinition": {
			"transactionCode": "01",
			"name": "start",
			"originalName": "Startpost",
			"properties": {
				"layoutName": {
					"length": 20,
					"startPos": 3,
					"endPos": 22,
					"format": "A:vb"
				},
				"version": {
					"length": 2,
					"startPos": 23,
					"endPos": 24,
					"format": "A:vb"
				},
				"timestamp": {
					"length": 20,
					"startPos": 25,
					"endPos": 44,
					"format": "N:-"
				},
				"enviromentTag": {
					"length": 1,
					"startPos": 45,
					"endPos": 45,
					"format": "A:-"
				}
			}
		},
		"properties": [
			{
				"name": "layoutName",
				"trimmedValue": "BGMAX",
				"rawValue": "BGMAX               ",
				"value": "BGMAX",
				"contentFormat": "A",
				"paddingFormat": "vb"
			},
			{
				"name": "version",
				"trimmedValue": "01",
				"rawValue": "01",
				"value": "01",
				"contentFormat": "A",
				"paddingFormat": "vb"
			},
			{
				"name": "timestamp",
				"trimmedValue": "20040525173035010331",
				"rawValue": "20040525173035010331",
				"value": 20040525173035012000,
				"contentFormat": "N",
				"paddingFormat": "-"
			},
			{
				"name": "enviromentTag",
				"trimmedValue": "P",
				"rawValue": "P",
				"value": "P",
				"contentFormat": "A",
				"paddingFormat": "-"
			}
		]
	},
	{
		"transactionCode": "05",
		"entryDefinition": {
			"transactionCode": "05",
			"name": "chapterStart",
			"originalName": "Öppningspost",
			"properties": {
				"recipientBankgiroNumber": {
					"length": 10,
					"startPos": 3,
					"endPos": 12,
					"format": "N:h0"
				},
				"recipientPlusgiroNumber": {
					"length": 10,
					"startPos": 13,
					"endPos": 22,
					"format": "N:h0/A:b"
				},
				"currency": {
					"length": 3,
					"startPos": 23,
					"endPos": 25,
					"format": "A:b"
				}
			}
		},
		"properties": [
			{
				"name": "recipientBankgiroNumber",
				"trimmedValue": "9912346",
				"rawValue": "0009912346",
				"value": 9912346,
				"contentFormat": "N",
				"paddingFormat": "h0"
			},
			{
				"name": "recipientPlusgiroNumber",
				"trimmedValue": "",
				"rawValue": "          ",
				"value": "",
				"contentFormat": "A",
				"paddingFormat": "b"
			},
			{
				"name": "currency",
				"trimmedValue": "SEK",
				"rawValue": "SEK",
				"value": "SEK",
				"contentFormat": "A",
				"paddingFormat": "b"
			}
		]
	},
	{
		"transactionCode": "26",
		"entryDefinition": {
			"transactionCode": "26",
			"name": "name",
			"originalName": "Namnpost",
			"properties": {
				"payerName": {
					"length": 35,
					"startPos": 3,
					"endPos": 37,
					"format": "A:vb"
				},
				"extraNameField": {
					"length": 35,
					"startPos": 38,
					"endPos": 72,
					"format": "A:vb"
				}
			}
		},
		"properties": [
			{
				"name": "payerName",
				"trimmedValue": "Kalles Plåt AB",
				"rawValue": "Kalles Plåt AB                     ",
				"value": "Kalles Plåt AB",
				"contentFormat": "A",
				"paddingFormat": "vb"
			},
			{
				"name": "extraNameField",
				"trimmedValue": "",
				"rawValue": "                                   ",
				"value": "",
				"contentFormat": "A",
				"paddingFormat": "vb"
			}
		]
	},
	{
		"transactionCode": "27",
		"entryDefinition": {
			"transactionCode": "27",
			"name": "address1",
			"originalName": "Adresspost",
			"properties": {
				"payerAddress": {
					"length": 35,
					"startPos": 3,
					"endPos": 37,
					"format": "A:vb"
				},
				"payerPostalCode": {
					"length": 9,
					"startPos": 38,
					"endPos": 46,
					"format": "A:vb"
				}
			}
		},
		"properties": [
			{
				"name": "payerAddress",
				"trimmedValue": "Storgatan 2",
				"rawValue": "Storgatan 2                        ",
				"value": "Storgatan 2",
				"contentFormat": "A",
				"paddingFormat": "vb"
			},
			{
				"name": "payerPostalCode",
				"trimmedValue": "12345",
				"rawValue": "12345    ",
				"value": "12345",
				"contentFormat": "A",
				"paddingFormat": "vb"
			}
		]
	},
	{
		"transactionCode": "28",
		"entryDefinition": {
			"transactionCode": "28",
			"name": "address2",
			"originalName": "Adresspost 2",
			"properties": {
				"payerAddress": {
					"length": 35,
					"startPos": 3,
					"endPos": 37,
					"format": "A:vb"
				},
				"payerCountry": {
					"length": 35,
					"startPos": 38,
					"endPos": 72,
					"format": "A:vb"
				},
				"payerCountryCode": {
					"length": 2,
					"startPos": 73,
					"endPos": 74,
					"format": "A:vb"
				}
			}
		},
		"properties": [
			{
				"name": "payerAddress",
				"trimmedValue": "Storåker",
				"rawValue": "Storåker                           ",
				"value": "Storåker",
				"contentFormat": "A",
				"paddingFormat": "vb"
			},
			{
				"name": "payerCountry",
				"trimmedValue": "",
				"rawValue": "                                   ",
				"value": "",
				"contentFormat": "A",
				"paddingFormat": "vb"
			},
			{
				"name": "payerCountryCode",
				"trimmedValue": "",
				"rawValue": "  ",
				"value": "",
				"contentFormat": "A",
				"paddingFormat": "vb"
			}
		]
	},
	{
		"transactionCode": "29",
		"entryDefinition": {
			"transactionCode": "29",
			"name": "address2",
			"originalName": "Adresspost 2",
			"properties": {
				"organisationNumber": {
					"length": 12,
					"startPos": 3,
					"endPos": 14,
					"format": "N:h0"
				}
			}
		},
		"properties": [
			{
				"name": "organisationNumber",
				"trimmedValue": "5500001234",
				"rawValue": "005500001234",
				"value": 5500001234,
				"contentFormat": "N",
				"paddingFormat": "h0"
			}
		]
	},
	{
		"transactionCode": "26",
		"entryDefinition": {
			"transactionCode": "26",
			"name": "name",
			"originalName": "Namnpost",
			"properties": {
				"payerName": {
					"length": 35,
					"startPos": 3,
					"endPos": 37,
					"format": "A:vb"
				},
				"extraNameField": {
					"length": 35,
					"startPos": 38,
					"endPos": 72,
					"format": "A:vb"
				}
			}
		},
		"properties": [
			{
				"name": "payerName",
				"trimmedValue": "Kalles Plåt AB",
				"rawValue": "Kalles Plåt AB                     ",
				"value": "Kalles Plåt AB",
				"contentFormat": "A",
				"paddingFormat": "vb"
			},
			{
				"name": "extraNameField",
				"trimmedValue": "",
				"rawValue": "                                   ",
				"value": "",
				"contentFormat": "A",
				"paddingFormat": "vb"
			}
		]
	},
	{
		"transactionCode": "27",
		"entryDefinition": {
			"transactionCode": "27",
			"name": "address1",
			"originalName": "Adresspost",
			"properties": {
				"payerAddress": {
					"length": 35,
					"startPos": 3,
					"endPos": 37,
					"format": "A:vb"
				},
				"payerPostalCode": {
					"length": 9,
					"startPos": 38,
					"endPos": 46,
					"format": "A:vb"
				}
			}
		},
		"properties": [
			{
				"name": "payerAddress",
				"trimmedValue": "Storgatan 2",
				"rawValue": "Storgatan 2                        ",
				"value": "Storgatan 2",
				"contentFormat": "A",
				"paddingFormat": "vb"
			},
			{
				"name": "payerPostalCode",
				"trimmedValue": "12345",
				"rawValue": "12345    ",
				"value": "12345",
				"contentFormat": "A",
				"paddingFormat": "vb"
			}
		]
	},
	{
		"transactionCode": "28",
		"entryDefinition": {
			"transactionCode": "28",
			"name": "address2",
			"originalName": "Adresspost 2",
			"properties": {
				"payerAddress": {
					"length": 35,
					"startPos": 3,
					"endPos": 37,
					"format": "A:vb"
				},
				"payerCountry": {
					"length": 35,
					"startPos": 38,
					"endPos": 72,
					"format": "A:vb"
				},
				"payerCountryCode": {
					"length": 2,
					"startPos": 73,
					"endPos": 74,
					"format": "A:vb"
				}
			}
		},
		"properties": [
			{
				"name": "payerAddress",
				"trimmedValue": "Storåker",
				"rawValue": "Storåker                           ",
				"value": "Storåker",
				"contentFormat": "A",
				"paddingFormat": "vb"
			},
			{
				"name": "payerCountry",
				"trimmedValue": "",
				"rawValue": "                                   ",
				"value": "",
				"contentFormat": "A",
				"paddingFormat": "vb"
			},
			{
				"name": "payerCountryCode",
				"trimmedValue": "",
				"rawValue": "  ",
				"value": "",
				"contentFormat": "A",
				"paddingFormat": "vb"
			}
		]
	},
	{
		"transactionCode": "20",
		"entryDefinition": {
			"transactionCode": "20",
			"name": "payment",
			"originalName": "Betalningspost",
			"properties": {
				"senderBankgiroNumber": {
					"length": 10,
					"startPos": 3,
					"endPos": 12,
					"format": "N:h0"
				},
				"reference": {
					"length": 25,
					"startPos": 13,
					"endPos": 37,
					"formatMap": {
						"0": "-:-",
						"1": "-:-",
						"2": "N:hb",
						"3": "A:-",
						"4": "A:vb",
						"5": "A:-"
					},
					"format": "N:hb"
				},
				"paymentAmount": {
					"length": 18,
					"startPos": 38,
					"endPos": 55,
					"format": "N:h0"
				},
				"referenceCode": {
					"length": 1,
					"startPos": 56,
					"endPos": 56,
					"format": "N:-"
				},
				"paymentMethod": {
					"length": 1,
					"startPos": 57,
					"endPos": 57,
					"format": "N:-",
					"possibleValues": {
						"1": "Betalningen är en elektronisk betalning från bank.",
						"2": "Betalningen är en elektronisk betalning från tjänsten Leverantörsbetalningar (LB).",
						"3": "Betalningen är en blankettbetalning",
						"4": "Betalningen är en elektronisk betalning från tjänsten Autogiro (AG)."
					}
				},
				"BGCSerialNumber": {
					"length": 12,
					"startPos": 58,
					"endPos": 69,
					"format": "N:-"
				},
				"aviImage": {
					"length": 1,
					"startPos": 70,
					"endPos": 70,
					"format": "N:-",
					"possibleValues": {
						"0": "Ingen avibild finns. Innebär att betalning har gjorts elektroniskt eller med OCR-avi.",
						"1": "Avibild finns. Innebär att betalning gjorts med girering-/inbetalningsavi.",
						"2": "Reserverade för framtida bruk"
					}
				}
			}
		},
		"properties": [
			{
				"name": "senderBankgiroNumber",
				"trimmedValue": "3783511",
				"rawValue": "0003783511",
				"value": 3783511,
				"contentFormat": "N",
				"paddingFormat": "h0"
			},
			{
				"name": "reference",
				"trimmedValue": "655969",
				"rawValue": "                   655969",
				"value": 655969,
				"contentFormat": "N",
				"paddingFormat": "hb"
			},
			{
				"name": "paymentAmount",
				"trimmedValue": "100000",
				"rawValue": "000000000000100000",
				"value": 100000,
				"contentFormat": "N",
				"paddingFormat": "h0"
			},
			{
				"name": "referenceCode",
				"trimmedValue": "2",
				"rawValue": "2",
				"value": 2,
				"contentFormat": "N",
				"paddingFormat": "-"
			},
			{
				"name": "paymentMethod",
				"trimmedValue": "2",
				"rawValue": "2",
				"value": 2,
				"contentFormat": "N",
				"paddingFormat": "-"
			},
			{
				"name": "BGCSerialNumber",
				"trimmedValue": "000000000010",
				"rawValue": "000000000010",
				"value": 10,
				"contentFormat": "N",
				"paddingFormat": "-"
			},
			{
				"name": "aviImage",
				"trimmedValue": "0",
				"rawValue": "0",
				"value": 0,
				"contentFormat": "N",
				"paddingFormat": "-"
			}
		]
	},
	{
		"transactionCode": "21",
		"entryDefinition": {
			"transactionCode": "21",
			"name": "deduction",
			"originalName": "Avdragspost",
			"properties": {
				"senderBankgiroNumber": {
					"length": 10,
					"startPos": 3,
					"endPos": 12,
					"format": "N:h0"
				},
				"reference": {
					"length": 25,
					"startPos": 13,
					"endPos": 37,
					"formatMap": {
						"0": "-:-",
						"1": "-:-",
						"2": "N:hb",
						"3": "A:-",
						"4": "A:vb",
						"5": "A:-"
					},
					"format": "A:-"
				},
				"paymentAmount": {
					"length": 18,
					"startPos": 38,
					"endPos": 55,
					"format": "N:h0"
				},
				"referenceCode": {
					"length": 1,
					"startPos": 56,
					"endPos": 56,
					"format": "N:-"
				},
				"paymentMethod": {
					"length": 1,
					"startPos": 57,
					"endPos": 57,
					"format": "N:-",
					"possibleValues": {
						"1": "Betalningen är en elektronisk betalning från bank.",
						"2": "Betalningen är en elektronisk betalning från tjänsten Leverantörsbetalningar (LB).",
						"3": "Betalningen är en blankettbetalning",
						"4": "Betalningen är en elektronisk betalning från tjänsten Autogiro (AG)."
					}
				},
				"BGCSerialNumber": {
					"length": 12,
					"startPos": 58,
					"endPos": 69,
					"format": "N:-"
				},
				"aviImage": {
					"length": 1,
					"startPos": 70,
					"endPos": 70,
					"format": "N:-",
					"possibleValues": {
						"0": "Ingen avibild finns. Innebär att betalning har gjorts elektroniskt eller med OCR-avi.",
						"1": "Avibild finns. Innebär att betalning gjorts med girering-/inbetalningsavi.",
						"2": "Reserverade för framtida bruk"
					}
				},
				"deductionCode": {
					"length": 1,
					"startPos": 71,
					"endPost": 71,
					"format": "N:-"
				}
			}
		},
		"properties": [
			{
				"name": "senderBankgiroNumber",
				"trimmedValue": "3783511",
				"rawValue": "0003783511",
				"value": 3783511,
				"contentFormat": "N",
				"paddingFormat": "h0"
			},
			{
				"name": "reference",
				"trimmedValue": "89853                    ",
				"rawValue": "89853                    ",
				"value": "89853                    ",
				"contentFormat": "A",
				"paddingFormat": "-"
			},
			{
				"name": "paymentAmount",
				"trimmedValue": "50000",
				"rawValue": "000000000000050000",
				"value": 50000,
				"contentFormat": "N",
				"paddingFormat": "h0"
			},
			{
				"name": "referenceCode",
				"trimmedValue": "3",
				"rawValue": "3",
				"value": 3,
				"contentFormat": "N",
				"paddingFormat": "-"
			},
			{
				"name": "paymentMethod",
				"trimmedValue": "2",
				"rawValue": "2",
				"value": 2,
				"contentFormat": "N",
				"paddingFormat": "-"
			},
			{
				"name": "BGCSerialNumber",
				"trimmedValue": "000230000111",
				"rawValue": "000230000111",
				"value": 230000111,
				"contentFormat": "N",
				"paddingFormat": "-"
			},
			{
				"name": "aviImage",
				"trimmedValue": "0",
				"rawValue": "0",
				"value": 0,
				"contentFormat": "N",
				"paddingFormat": "-"
			},
			{
				"name": "deductionCode",
				"trimmedValue": "0         ",
				"rawValue": "0         ",
				"value": 0,
				"contentFormat": "N",
				"paddingFormat": "-"
			}
		]
	}
]
```
</details>



### Files & Folders

- example-files - Contains example files downloaded from https://www.bankgirot.se/kundservice/exempelfiler/ (latin1 encoding)
- tests - Contains Jest test files
- index.js - The parser

### Links to the information used to build this parser
- https://www.bankgirot.se/en/services/incoming-payments/bankgiro-receivables/ - Information about the service "Bankgiro Receivables (Bankgiro Inbetalningar)"
- https://www.bankgirot.se/globalassets/dokument/tekniska-manualer/bankgiroinbetalningar_tekniskmanual_sv.pdf - Technical Manual (SV) for "Bankgiro inbetalningar". Everything used to create this parser is detailed in this document.
- https://www.bankgirot.se/globalassets/dokument/tekniska-manualer/bankgiroreceivables_bankgiroinbetalningar_technicalmanual_en.pdf - Translation to English of the Technical Manual. This was not used when creating this parser but should contain the same information.