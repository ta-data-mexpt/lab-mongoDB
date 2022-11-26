1. 
Filer: { name: { $eq: 'Babelgum' } }
Project: {name: 1}
Sort: 
Collation:

2. 
Filter: { number_of_employees: { $gt: 5000 } }
Project: 
Sort: { number_of_employees: -1}
Collation:
Limit: 20

3. 
Filter: { $and: [{ founded_year: { $gte: 2000}}, { founded_year: { $lte: 2005}} ]}
Project: {name: 1, founded_year: 1}
Sort: 
Collation:

4. 
Filter: { $and: [{ "ipo.valuation_amount": {$gt: 100000000}}, { founded_year: { $lt: 2005}} ]}
Project:  {name: 1, ipo: 1}
Sort: 
Collation:

5. 
Filter: { $and: [{ "number_of_employees": {$lt: 1000}}, { founded_year: { $lt: 2005}} ]}
Project: 
Sort: {number_of_employees: -1}
Collation:
Limit: 10

6. 
Filter: { partners: { $exists: false } } 
Project: 
Sort: 
Collation:

7. 
Filter: { category_code: { $type: 'null'}}
Project: 
Sort: 
Collation:

8. 
Filter: { $and: [{ number_of_employees: { $gte: 100}}, { number_of_employees: { $lt: 1000}} ]}
Project: {name: 1, number_of_employees: 1}
Sort: 
Collation:


9. 
Filter: {"ipo.valuation_amount": {$ne: null}}
Project: 
Sort: {"ipo.valuation_amount": -1}
Collation:

10. 
Filter: {number_of_employees: {$ne: null}}
Project: {name: 1}
Sort: {number_of_employees:-1}
Collation:
Limit: 10

11. 
Filer: {founded_month: {$gte: 6}}
Project: 
Sort: 
Collation:
Limit: 1000


12. 
Filter:  {$expr: {$gt:[deadpooled_year, founded_year("3")]}}
Project: 
Sort: 
Collation:

13. 
Filter: { $and: [{'founded_year': {$lt:2000}},{'acquisition.price_amount': {$gt:10000000}}]}
Project: 
Sort: 
Collation:

14. 
Filter: {"acquisition.acquired_year": {$gt:2015}}
Project: {name: 1,acquisition:1}
Sort: {"acquisition.price_amount":-1}
Collation:

15. 
Filter: 
Project: {name: 1,founded_year:1}
Sort: {founded_year: -1}
Collation:

16. 
Filter: {founded_day:{$lte:7}}
Project: 
Sort: {"acquisitions.price_amount":1, "acquisition.price_amount":1}
Collation:
Limit: 10

17. 
Filter: {$and: [{category_code: {$eq: "web"}}, {number_of_employees: {$gt: 4000}}]} 
Project: 
Sort: {number_of_employees: 1}
Collation:

18. 
Filter: {$and:[ {"acquisition.price_amount": {$gt: 10000000}}, {"acquisition.price_currency_code": {$eq: 'EUR'}}]}
Project: 
Sort: 
Collation:


19. 
Filter: {"acquisition.acquired_month": {$lte: 3}} 
Project: {name:1, acquisition:1}
Sort: 
Collation:

20. 
Filter: {$and: [{founded_year: {$gte: 2000}}, {founded_year: {$lte:2010}}, {"acquisition.acquired_year": {$eq: "null"}}]}
Project: 
Sort: 
Collation:
