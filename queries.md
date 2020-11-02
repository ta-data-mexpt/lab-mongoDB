1. All the companies that it's name match 'Babelgum'. Retrieve only their name field.
FILTER:{name:'Babelgum'}
PROJECT:{name:1,_id:0}

name:"Babelgum"

2. All the companies that have more than 5000 employees. Limit the search to 20 companies and sort them by number of employees.
FILTER: {number_of_employees:{$gt:5000}}
PROJECT: {name:1,_id:0,number_of_employees:1}
SORT: {number_of_employees:-1}
LIMIT: 20

name:"Siemens"
number_of_employees:405000
name:"IBM"
number_of_employees:388000
name:"Toyota"
number_of_employees:320000
name:"PayPal"
number_of_employees:300000
name:"Nippon Telegraph and Telephone Corporation"
number_of_employees:227000
name:"Samsung Electronics"
number_of_employees:221726
name:"Accenture"
number_of_employees:205000
name:"Tata Consultancy Services"
number_of_employees:200300
name:"Flextronics International"
number_of_employees:200000
name:"Safeway"
number_of_employees:186000
name:"Sony"
number_of_employees:180500
name:"LG"
number_of_employees:177000
name:"Ford"
number_of_employees:171000
name:"Boeing"
number_of_employees:160000
name:"Digital Equipment Corporation"
number_of_employees:140000
name:"Nokia"
number_of_employees:125000
name:"MItsubishi Electric"
number_of_employees:107000
name:"MItsubishi Electric"
number_of_employees:107000
name:"Comcast"
number_of_employees:100000
name:"Bertelsmann"
number_of_employees:100000

3. All the companies founded between 2000 and 2005, both years included. Retrieve only the name and founded_year fileds.
FILTER:{founded_year:{$gte:2000,$lte:2005}}
PROJECT:{name:1,_id:0,founded_year:1}

name:"Wetpaint"
founded_year:2005
name:"Zoho"
founded_year:2005
name:"Digg"
founded_year:2004
name:"Facebook"
founded_year:2004
name:"Omnidrive"
founded_year:2005
...

4. All the companies that had a Valuation Amount of more than 100.000.000 and have been founded before 2010. Retrieve only the name and ipo fields.
FILTER:{'ipo.valuation_amount':{$gt:100000000},'founded_year':{$lt:2010}}
PROJECT:{name:1,_id:0,ipo:1}

name:"Facebook"
valuation_amount:104000000000
valuation_currency_code:"USD"
pub_year:2012
pub_month:5
pub_day:18
stock_symbol:"NASDAQ:FB"
name:"Twitter"
valuation_amount:18100000000
valuation_currency_code:"USD"
pub_year:2013
pub_month:11
pub_day:7
stock_symbol:"NYSE:TWTR"
...

5. All the companies that have less than 1000 employees and have been founded before 2005. Order them by the number of employees and limit the search to 10 companies.
FILTER:{number_of_employees:{$lt:1000},founded_year:{$lt:2005}}
PROJECT:{name:1,_id:0,founded_year:1,number_of_employees:1}
SORT:{number_of_employees:-1}
LIMIT:10

name:"Infinera Corporation"
number_of_employees:974
founded_year:2000
name:"NorthPoint Communications Group"
number_of_employees:948
founded_year:1997
name:"888 Holdings"
number_of_employees:931
founded_year:1997
name:"Forrester Research"
number_of_employees:903
founded_year:1983
name:"SonicWALL"
number_of_employees:900
founded_year:1991
name:"Webmetrics"
number_of_employees:900
founded_year:1999
name:"Cornerstone OnDemand"
number_of_employees:881
founded_year:1999
name:"Mozilla"
number_of_employees:800
founded_year:1998
name:"Buongiorno"
number_of_employees:800
founded_year:1999
name:"Yelp"
number_of_employees:800
founded_year:2004

6. All the companies that don't include the partners field.
FILTER:{partners:{$exists:false}}

No results

7. All the companies that have a null type of value on the category_code field.
FILTER:{category_code:null}
PROJECT:{name:1,_id:0,category_code:1}

name:"Collective"
category_code:null
name:"Snimmer"
category_code:null
name:"KoolIM"
category_code:null
name:"Level9 Media"
category_code:null
name:"VidKing"
category_code:null
...

8. All the companies that have at least 100 employees but less than 1000. Retrieve only the name and number of employees fields.
#No supe cómo poner las dos condiciones
FILTER:{number_of_employees:{number_of_employees:{$gte:100}}
PROJECT:{name:1,_id:0,number_of_employees:1}

name:"AdventNet"
number_of_employees:600
name:"Zoho"
number_of_employees:1600
name:"Facebook"
number_of_employees:5299
...

9. Order all the companies by their IPO price descendently.
PROJECT:{name:1,_id:0,'ipo.valuation_amount':1}
SORT:{"ipo.valuation_amount":-1}

name:"GREE"
valuation_amount:108960000000
name:"Facebook"
valuation_amount:104000000000
name:"Amazon"
valuation_amount:100000000000
...

10.Retrieve the 10 companies with more employees, order by the number of employees.
PROJECT:{name:1,_id:0,number_of_employees:1}
SORT:{number_of_employees:-1}
LIMIT:10

name:"Siemens"
number_of_employees:405000
name:"IBM"
number_of_employees:388000
name:"Toyota"
number_of_employees:320000
name:"PayPal"
number_of_employees:300000
name:"Nippon Telegraph and Telephone Corporation"
number_of_employees:227000
name:"Samsung Electronics"
number_of_employees:221726
name:"Accenture"
number_of_employees:205000
name:"Tata Consultancy Services"
number_of_employees:200300
name:"Flextronics International"
number_of_employees:200000
name:"Safeway"
number_of_employees:186000

11. All the companies founded on the second semester of the year. Limit your search to 1000 companies.
FILTER:{founded_month:{$gte:7}}
PROJECT:{name:1,_id:0,founded_month:1}
LIMIT:1000

name:"Wetpaint"
founded_month:10
name:"Zoho"
founded_month:9
name:"Digg"
founded_month:10
name:"Omnidrive"
founded_month:11
...

12. All the companies that have been 'deadpooled' after the third year.
#No supe como hacer la resta entre el deadpooled year y el founded year :S
PROJECT: {name:1,_id:0,deadpooled_year:1,founded_year:1}

13. All the companies founded before 2000 that have and acquisition amount of more than 10.000.000.
FILTER:{founded_year:{$lt:2000},'acquisition.price_amount':{$gte:10000000}}
PROJECT:{name:1,_id:0,founded_year:1,"acquisition.price_amount":1}

name:"Postini"
founded_year:1999
price_amount:625000000
name:"SideStep"
founded_year:1999
price_amount:180000000
name:"Recipezaar"
founded_year:1999
price_amount:25000000
...

14. All the companies that have been acquired after 2015, order by the acquisition amount, and retrieve only their name and acquisiton field.
FILTER:{'acquisition.acquired_year':{$gt:2015}}
PROJECT:{name:1,_id:0,acquisition:1}
SORT:{'acquisition.price_amount':-1}

No results

15. Order the companies by their founded year, retrieving only their name and founded year.
FILTER:{founded_year:{$not:{$eq:null}}}
PROJECT:{name:1,_id:0,founded_year:1}
SORT:{founded_year:1}

name:"US Army"
founded_year:1800
name:"Alstrasoft"
founded_year:1800
name:"SmallWorlds"
founded_year:1800
name:"DuPont"
founded_year:1802
...

16. All the companies that have been founded on the first seven days of the month, including the seventh. Sort them by their aquisition price descendently. Limit the search to 10 documents.
FILTER:{founded_day:{$lte:7}}
PROJECT:{name:1,_id:0,founded_day:1,"acquisition.price_amount":1}
SORT:{"acquisition.price_amount":-1}
LIMIT:10

name:"Netscape"
founded_day:4
price_amount:4200000000
name:"PayPal"
founded_day:1
price_amount:1500000000
name:"Zappos"
founded_day:1
price_amount:1200000000
name:"Alibaba"
founded_day:1
price_amount:1000000000
name:"Postini"
founded_day:2
price_amount:625000000
name:"Danger"
founded_day:1
price_amount:500000000
name:"Clearwell Systems"
founded_day:6
price_amount:410000000
name:"PrimeSense"
founded_day:1
price_amount:345000000
name:"Amobee"
founded_day:1
price_amount:321000000
name:"BlueLithium"
founded_day:1
price_amount:300000000

17. All the companies on the 'web' category that have more than 4000 employees. Sort them by the amount of employees in ascendant order.
FILTER:{category_code:{$eq:'web'},number_of_employees:{$gt:4000}}
PROJECT:{name:1,_id:0,number_of_employees:1}
SORT:{number_of_employees:1}

name:"Expedia"
number_of_employees:4400
name:"AOL"
number_of_employees:8000
name:"Webkinz"
number_of_employees:8657
name:"Rakuten"
number_of_employees:10000
name:"Los Angeles Times Media Group"
number_of_employees:10000
name:"Groupon"
number_of_employees:10000
name:"Yahoo!"
number_of_employees:13600
name:"eBay"
number_of_employees:15000
name:"Experian"
number_of_employees:15500

18. All the companies which their acquisition amount is more than 10.000.000, and currency are 'EUR'.
FILTER:{"acquisition.price_amount":{$gt:10000000},"acquisition.price_currency_code":'EUR'}
PROJECT:{name:1,_id:0,"acquisition.price_amount":1,"acquisition.price_currency_code":1}

name:"ZYB"
price_amount:31500000
price_currency_code:"EUR"
name:"Apertio"
price_amount:140000000
price_currency_code:"EUR"
name:"Greenfield Online"
price_amount:40000000
price_currency_code:"EUR"
name:"Webedia"
price_amount:70000000
price_currency_code:"EUR"
name:"Wayfinder"
price_amount:24000000
price_currency_code:"EUR"
name:"Tuenti Technologies"
price_amount:70000000
price_currency_code:"EUR"
name:"BioMed Central"
price_amount:43400000
price_currency_code:"EUR"

19. All the companies that have been acquired on the first trimester of the year. Limit the search to 10 companies, and retrieve only their name and acquisition fields.
FILTER:{'acquisition.acquired_month':{$lte:3}}
PROJECT:{name:1,_id:0,acquisition:1}
LIMIT:10

name:"Kyte"
price_amount:null
price_currency_code:"USD"
term_code:null
source_url:"http://techcrunch.com/2011/01/31/exclusive-kit-digital-acquires-kickap..."
source_description:"KIT digital Acquires KickApps, Kewego AND Kyte For $77.2 Million"
acquired_year:2011
acquired_month:1
acquired_day:31
name:"NetRatings"
price_amount:327000000
price_currency_code:"USD"
term_code:"cash"
source_url:"http://login.vnuemedia.com/hr/login/login_subscribe.jsp?id=0oqDem1gYIf..."
source_description:"Nielsen buys rest of NetRatings"
acquired_year:2007
acquired_month:2
acquired_day:null
name:"blogTV"
price_amount:null
price_currency_code:"USD"
term_code:null
source_url:"http://techcrunch.com/2013/03/13/younow-buys-blogtv/"
source_description:"Live Social Video Network YouNow Acquires Streaming Service BlogTV"
acquired_year:2013
acquired_month:3
acquired_day:13
...

20. All the companies that have been founded between 2000 and 2010, but have not been acquired before 2011.
#No se como poner las tres condiciones :S
FILTER:{founded_year:{$gte:2000},founded_year:{$lte:2010},'acquisition.acquired_year':{$not:{$lt:2011}}}
PROJECT:{name:1,_id:0,founded_year:1,"acquisition.acquired_year":1}

name:"Wetpaint"
founded_year:2005
acquired_year:2013
name:"AdventNet"
founded_year:1996
name:"Zoho"
founded_year:2005
...

