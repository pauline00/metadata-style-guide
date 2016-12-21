![background sidebar image](https://github.com/kobolabs/metadata-style-guide/blob/Testing/banner-MSG3.png)

# Kobo Metadata Style Guide

## Table of Contents
### Required Field
* [eISBN](#eisbn) </br>
* [Title](#title) </br>
* [Publisher](#publisher)</br>
* [Contributor (Author, Editor, etc.)](#contributor-author-editor-etc)</br>
* [Language](#language)</br>
* [Subject Code](#subject-code)</br>
* [Sales Rights](#sales-rights)</br>
* [Price/Price Type Code (ONIX only)](#Price-Price-Type Code (ONIX only))</br>
* Price Date Role (ONIX only)</br>
* Publishing Status</br>

### Strongly Recommended
* Publication Date</br>
* On Sale Date (ONIX 2.1) / Embargo Date (ONIX 3.0)</br>
* Related Product</br>
* Series Name/Series Number</br>
* Audience Age Range - From/Audience Age Range - To</br>
* Product Availability</br>
* Master Brand</br>

### Recommended if applicable
* Subtitle</br>
* Imprint</br>




</br></br>

## eISBN 

### Definition</br>
Your eBook's electronic ISBN. Must be 13 digits in length.
  
### Best Practice	</br>
> In ONIX the ISBN must be unhyphenated.

### Correct Usage (example)	</br>
               | Excel                                   | ONIX 2.1 and 3.0
-------------- | --------------------------------------- | --------------------------------------- 
**Reference Name** |eBook ISBN: 9780007322596                | `<ProductIdentifier>`</br>`<ProductIDType>03</ProductIDType>`</br>`<IDValue>9780826110077</IDValue>`</br>`</ProductIdentifier>`</br>`<productidentifier>`</br>   
**Short Tag**      | N/A                                     | `<b221>03</b221>`</br>`<b244>9780826110077</b244>`</br>`</productidentifier>` </br>       
**Character Limits**	|13 digits|13 digits
    
### :warning: Common Errors (example)	</br>
  * 9781780000
  * 978-1443424523

### Notes</br>
ONIX: `ProductIDType` 03 is mandatory as it represents how your books will be identified in universal trading transactions.  

Multiple Product Identifers are allowed per title. We parse `ProductIDs` of product types in this order: ‘03’, ‘15’, ‘02’, ‘01.’ Please note we will only use type ‘02’ in cases where neither type ‘03’, nor type ‘15’ is provided. 

When supplying ISBNs to the library sector, the ISBN-13 `ProductIDType` 15 should be labelled distinctively.   
</br>
02 - ISBN-10 </br>
03 - EAN-13 (GTIN-13) </br>
04 - UPC </br>
13 - LCCN </br>
15 - ISBN-13</br>

</br></br>
## Title

### Definition</br>
 Your eBook's title as it should appear on the Kobo store.
 
### Best Practice	</br>
> Please refrain from appending "A" or "The" to the end of the title as it might interfere with search functions. Also, please refrain from adding the subtitle in the title field and use the appropriate Excel field or ONIX tag.

### Correct Usage (example)	</br>
               | Excel                                   | ONIX 2.1                                | ONIX 3.0
-------------- | --------------------------------------- | --------------------------------------- |---------------------------------------
**Reference Name** |Title: The Shark in the Park| `<Title>`</br>`<TitleType>01</TitleType>`</br>`<TitleText>The Shark In The Park</TitleText>`</br>`</Title>`</br> |`<TitleDetail>`</br>`<TitleType>01</TitleType>`</br>`<TitleElement>`</br>`<TitleElementLevel>01</TitleElementLevel>`</br>`<TitlePrefix>The</TitlePrefix>`</br>`<TitleWithoutPrefix>Shark In The Park</TitleWithoutPrefix>`</br>`<Subtitle>Left Shark's Park Lark</Subtitle>`</br>`</TitleElement>`</br>`</TitleDetail>`</br>
**Short Tag**      | N/A|N/A|`<titledetail>`</br>`<b202>01</b202>`</br>`<titleelement>`</br>`<x409>01</x409>`</br>`<b030>The</b030>`</br>`<b031>Shark In The Park</b031>`</br>`<b029>Left Shark’s Park Lark</b029>`</br>`</titleelement>`</br>`</titledetail>`</br>      
**Character Limits**	|250|250|250

### :warning: Common Errors (example)	</br>
Incorrect: Fellowship of the Ring, The

</br></br>
## Publisher	

### Definition</br>
Your publisher name as it should appear on the Kobo store.

### Correct Usage (example)	</br>
               | Excel                       | ONIX 2.1 and 3.0
-------------- | --------------------------- | --------------------------- 
**Reference Name** |Publisher: Left Shark Editions|`<Publisher>`</br>`<PublishingRole>01</PublishingRole>`</br>`<PublisherName>Left Shark Editions</PublisherName>`</br>`</Publisher>`</br>
**Short Tag**      | N/A                            |`<publisher> `</br>`<b291>01</b291>`</br>`<b081>Left Shark Editions</b081>`</br>`</publisher>`</br>   
**Character Limits**	|250|250

</br></br>

## Contributor (Author, Editor, etc.)

### Definition</br>
The author and/or editor name(s)

### Best Practice	</br>
> Please use the format: First Name + Last Name for this field. No commas or name order reversal.
>
> ONIX: If your title does not have a contributor, you can now use the field <NoContributor/> or <n339/> in your ONIX. We will instead list the imprint or publisher name as the byline.

### Correct Usage (example)	</br>
               | Excel                       | ONIX 2.1 and 3.0
-------------- | --------------------------- | --------------------------- 
**Reference Name** |Contributor 1: David Shubert</br>Contributor Type: A01|`<Contributor>`</br>`<SequenceNumber>1</SequenceNumber>`</br>`<ContributorRole>A01</ContributorRole>`</br>`<PersonName>David Shubert PhD</PersonName>`</br>`<NamesBeforeKey>David</NamesBeforeKey>`</br>`<KeyNames>Shubert</KeyNames>`</br>`<LettersAfterNames>PhD</LettersAfterNames>`</br>`</Contributor>`</br>  
**Short Tag**      |N/A                             |`<contributor>`</br>`<b034>1</b034>`</br>`<b035>A01</b035>`</br>`<b036>Ben Byrne</b036>`</br>`<b037>Byrne, Ben</b037>`</br>`<b039>Ben</b039>`</br>`<b040>Byrne</b040>`</br>`<b251>GB</b251>`</br>`</contributor>`</br>   
**Character Limits**	|250|250
### :warning: Common Errors (example)	</br>
Incorrect: Shubert, David

### Notes</br>
Excel: This is where you can list the names of your eBook's contributors. If your title has multiple names for the same contributor type, you can list them within a single cell with each name separated by a comma.

</br></br>
## Language	
### Definition</br>
Excel: The language code that indicates the language in which your eBook is written (two characters).
ONIX: Language role (language of text, language of original text, etc) and the three-character language code. 
</br>
### Correct Usage (example)	</br>
               | Excel                       | ONIX 2.1 and 3.0
-------------- | --------------------------- | --------------------------- 
**Reference Name** | Language: EN                            | `<Language>`</br>`<LanguageRole>01</LanguageRole>`</br>`<LanguageCode>eng</LanguageCode>`</br>`</Language>`</br> 
**Short Tag**      | N/A                            |`<language>`</br>`<b253>01</b253>`</br>`<b252>eng</b252>`</br>`</language>`</br>    
**Character Limits**	|2|3
### :warning: Common Errors (example)	</br>
Excel: BRL, English, Eng 

### Notes</br>
Please note that currently we don't support multiple language codes for a single title. Please choose one specific language code for the text and include information about the bilingual nature of the text in the description. We suggest selecting the language code for the audience the title most widely serves. 
</br></br>
## Subject Code	
### Definition</br>
A subject category code from the scheme identified (BISAC, BIC, etc), which will help catalogue ebooks.

### Best Practice	</br>
> Please always include a subject code so customers can more easily find your ebooks. Category codes help discoverability on site. Your chosen codes correspond to our category stores on site, so the more specific you can be, the better.
> 
> While it's beneficial to have a main subject, please include additional subject codes with increasing precision so your target audience will find your books.

 
               | Excel                       | ONIX 2.1                   | ONIX 3.0
-------------- | --------------------------- | ---------------------------|---------------------------
**Reference Name** |Categorization Code:JNF001100</br>Categorization Type: BISAC                           |BISAC</br>`<BASICMainSubject> JNF001100</BASICMainSubject>`</br>`<Subject>`</br>`<SubjectSchemeIdentifier>10</SubjectSchemeIdentifier>`</br>`<SubjectCode>JNF028000</SubjectCode>`</br>`</Subject>`</br>BIC</br>`<BICMainSubject> YNU</BICMainSubject>`</br>                            |`<Subject>`</br>`<MainSubject/>`</br>`<SubjectSchemeIdentifier>10</SubjectSchemeIdentifier>`</br>`<SubjectCode> JNF001000</SubjectCode>`</br>`</Subject>`</br>`<Subject>`</br>`<SubjectSchemeIdentifier>10</SubjectSchemeIdentifier>`</br>`<SubjectCode> JNF028020</SubjectCode>`</br>`</Subject>`</br> 
**Short Tag**      |N/A                             |BISAC</br>`<b064> JNF001100</b064>`</br>`<subject>`</br>`<b067>10</b067>`</br>`<b069> JNF028000</b069>`</br>`<subject>`</br>BIC</br>`<b065>YNU</b065>`</br>                            |`<subject>`</br>`<x425/>`</br>`<b067>10</b067>`</br>`<b069> JNF001000</b069>`</br>`</subject>`</br>`<subject>`</br>`<b067>10</b067>`</br> 

### Notes</br>
Best practices recommend that books include at least 3 subject category codes to maximize customer reach.
We do not currently accept Thema codes. 
</br></br>
## Sales Rights	
### Definition</br>
Your eBook's sales rights.
 
### Best Practice	</br>
> To indicate sales rights use two-letter territory codes to specify where your ebook can be sold according to the rights your company holds. `<SalesRightsType>` is important in indicating specific type of rights held (exclusive, non-exclusive, not for sale, etc). Please see correct usage for how to declare sales rights in ONIX.</br>
>
> ONIX 2.1: Please use upper-case characters and separate each territory with a space in `<RightsCountry>US CA</RightsCountry>`. World Rights should be indicated as `<RightsTerritory>WORLD</RightsTerritory>`</br>
> ONIX 3.0: Similarly, in `<CountriesIncluded>` please use upper-case characters and separate each territory with a space. World rights should be indicated as `<RegionsIncluded>WORLD</RegionsIncluded>`</br>
>
> Excel: Leave this field blank if you have world rights. If your eBook can only be sold in a specific list of countries, you must indicate their two-letter country codes in this field with each country code separated by a comma.

### Correct Usage (example)	</br>
               | Excel                       | ONIX 2.1                   | ONIX 3.0
-------------- | --------------------------- | ---------------------------|---------------------------
**Reference Name** |US,CA,BR|`<SalesRights>`</br>`<SalesRightType>01</SalesRightsType>`</br>`<RightsCountry>US CA BR</RightsCountry>`</br>`</SalesRights>`</br>|`<SalesRights>`</br>`<SalesRightsType>01</SalesRightsType>`</br>`<Territory>`</br>`<CountriesIncluded>US CA BR</CountriesIncluded>`</br>`</Territory>`</br>`</SalesRights>`</br> 
**Short Tag**      |N/A|Short tag: `<salesrights>`</br>`<b089>01</b089>`</br>`<b090>US CA BR</b090>`</br>`</salesrights>`</br>                            |`<salesrights>`</br>`<b089>01</b089>`</br>`<territory>`</br>`<x449>US CA BR</x449>`</br>`</territory>`</br>`<salesrights>`</br> 

### :warning: Common Errors (example)	</br>
Excel: Australia

### Notes</br>
Kobo only supports 3 types of `<SalesRightsType>` (`<b089>`) values: 01 - for sale (exclusive rights) 02 - for sale (non-exclusive rights) 03 - not for sale
</br></br>

## Price/Price Type Code (ONIX only)	
### Definition</br>
Your eBook's price.

The Price Type Code specifies the type of price submitted (e.g. agency, wholesale, IPP).

### Best Practice	</br>
> **Price**

> In **ONIX**, please follow the 2.1 or 3.0 specification.

> In **Excel** price:</br>
  > * Must not contain commas.</br>
  > * Must be formatted as a number.</br>
  > * Must not contain currency symbols.</br>
  > * Currency must be in upper-case format.</br>

> **Price Type Code**

> Please submit prices that correspond with your territory and contract type. For prices that don't have tax included (applicable to CA, US), our system will automatically add taxes upon customer checkout. Please see below for a list of important price type codes.</br>

> **`<PriceType>`**

> Codes</br>
> Prices without tax included (CA and US)</br>
> 01 – Wholesale prices in Canada and the US, without tax included</br>
> 41 – Agency prices in Canada and the US, without tax included</br>
> 03 – IPP prices in Canada and the US, without tax included</br>
</br>
> Prices with tax included (EU, UK, and AU)</br>
> 02 – Wholesale prices in the EU, UK, and AU, with tax included</br>
> 42 – Agency prices in the EU, UK, and AU, with tax included</br>
> 04 – IPP prices in the EU, UK, and AU, with tax included" </br>

### Correct Usage (example)	</br>
 
               | Excel                       | ONIX 2.1                   | ONIX 3.0
-------------- | --------------------------- | ---------------------------|---------------------------
**Reference Name** |Price: 7.99</br>Currency: CAD|`<price> `</br>`<PriceTypeCode>41</PriceTypeCode> `</br>`<PriceAmount>12.99</PriceAmount> `</br>`<CurrencyCode>CAD</CurrencyCode> `</br>`</price> `</br>|`<price> `</br>`<PriceType>02>/<PriceType> `</br>`<PriceAmount>13.99</PriceAmount> `</br>`<CurrencyCode>GBP</CurrencyCode> `</br>`</price> `</br> 
**Short Tag**      |N/A|`<price> `<j148>41</j148> `</br>`<j151>12.99</j151> `</br>`<j152>CAD</j152> `</br>`</price> |`<price> `</br>`<x462>02</462> `</br>`<j151>13.99</j151> `</br>`<j152>GBP</j152> `</br>`</price>`</br> 

### :warning: Common Errors (example)	</br>
  * Incorrect price: $3.99</br>
  * Incorrect price: 1,299.99</br>
  * Incorrect currency in Excel: cad, CA</br>

### Notes</br>
**Excel and ONIX**: JPY prices must be listed as a whole number with zero decimal values. Hiding decimal places with values other than zero will cause your entry to **fail**. 

MXN prices must also be listed as whole numbers with zero decimal values. For MXN pricing, if decimals are provided, the prices will be rounded up or down (e.g. 249.25 MXN will be rounded to 249 MXN, while 249.75 MXN will be rounded to 250 MXN). 

In both Excel and ONIX free titles must be listed with a 0 or 0.00 value. In ONIX, the Unpriced Item Type code is accepted for free titles when used correctly.
</br></br>
--- template --- 

## Field	
### Definition</br>


### Best Practice	</br>
> 

### Correct Usage (example)	</br>
               | Excel                       | ONIX 2.1 and 3.0
-------------- | --------------------------- | --------------------------- 
**Reference Name** |                             | 
**Short Tag**      |                             |   
**Character Limits**	|250|250
 
               | Excel                       | ONIX 2.1                   | ONIX 3.0
-------------- | --------------------------- | ---------------------------|---------------------------
**Reference Name** |                             |                            | 
**Short Tag**      |                             |                            | 
**Character Limits**	|250                   |250                         |250
### :warning: Common Errors (example)	</br>

### Notes</br>
</br></br>
--- template --- 
