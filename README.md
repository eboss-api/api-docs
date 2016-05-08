EBOSS REST API Documentation
==================


Introduction
------------
This is the documentation for the EBOSS REST API. The API allows EBOSS suppliers to access brand and product data for website, mobile application, or other information system integration.


Authors
-------
Tim Klein, Dodat Ltd., tim[at]dodat[dot]co[dot]nz


License
-------
This wrapper is released under the MIT License.

Copyright (c) 2016 EBOSS. Copyright (c) 2016 Dodat Ltd.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.


Authentication
--------------
To access the API you need to provide authentication via HTTP Auth.

Please [contact EBOSS](https://www.eboss.co.nz/contact) if you are an EBOSS supplier and would like access to the API.

Once approved, EBOSS will supply you with an api username, api key, and brand id number.


Access Limitations
------------------
Currently the EBOSS REST API allows for a maxiumum of 1000 (one thousand) requests per hour, we recommend any application built utilising the EBOSS REST API take advanatage of client side caching to make the best use of data requests and to speed up your application.


Example Implementation
----------------------
For an example implementation, please see our [php wrapper class](https://github.com/eboss-api/php-wrapper).

Wrappers for other programming languages (.NET, Ruby on Rail, Python) may be created using the below REST API endpoint methods.
Please consider open sourcing and contributing your code back to the EBOSS API repository if you create something useful.


API Endpoint
------------
Please use https://www.eboss.co.nz/api/v2/ as the API endpoint.

This requires HTTP Auth to access passing in the api username and api key credentials provided.


Response format
---------------
The response is formated as a JSON object.


Core Objects and API Endpoints
------------------------------

**Brand**

Returns brand information associated with certain BRANDID.

https://www.eboss.co.nz/api/v2/Brand?BrandID=BRANDID


**Categories**

Returns list of products for BRANDID.

https://www.eboss.co.nz/api/v2/Categories?BrandID=BRANDID


**Category**

Returns details about CATEGORYID with respect to the BRANDID scope.

https://www.eboss.co.nz/api/v2/Category?BrandID=BRANDID&CategoryID=CATEGORYID


**Ranges**

Returns list of ranges associated with BRANDID scope.

https://www.eboss.co.nz/api/v2/Ranges?BrandID=BRANDID


**Range**

Returns details about RANGEID associated with BRANDID scope.

https://www.eboss.co.nz/api/v2/Range?BrandID=BRANDID&RangeID=RANGEID


**Products**

Returns list of products from BRANDID scope.

https://www.eboss.co.nz/api/v2/Products?BrandID=BRANDID

Also allows optional filters to be added:

CategoryID - CATEGORYID, which returns all products within a category.

RangeID - RANGEID, which returns all products within a range.

Example:

https://www.eboss.co.nz/api/v2/Products?BrandID=BRANDID&CategoryID=CATEGORYID&RangeID=RANGEID


**Product**

Returns individual product data with PRODUCTID and associated details from BRANDID.

https://www.eboss.co.nz/api/v2/Product?BrandID=BRANDID&ProductID=PRODUCTID

