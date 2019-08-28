<a href='https://smartpay.curexe.com'><img src="https://smartpay.curexe.com/resources/img/logo.png" width="200" ></a>

## Overview

The SmartPay Checkout solution consists of an iFrame, an API and the SmartPay website. This documentation covers the installation and use of the iFrame, which captures consumer detail which can then be accessed by retailers through the API.

<img src="diagram.png">

# Installing the iFrame

Installing the SmartPay app on your website requires using an iframe. [Need help with HTML?](https://www.w3schools.com/tags/tag_iframe.asp)

Styling the iframe: we recommend setting the border to 0, width to 100% and height to minimum of 500px.

Configuration values are passed to the SmartPay app using thr <a href="https://en.wikipedia.org/wiki/Query_string">query string</a> on the iframe url.

Here is an example of a url used on the iframe:

```
https://smartpay.curexe.com/iframe.php?key=abc123&singleAmt=50&curr=CAD (etc.)
```

All parameter/value pairs must be separated with an ampersand (&). All values should be URL-encoded.

# Input Parameters

The following input parameters are available for use in the iframe:

<table>
<thead>
<tr>
<th>Parameter<sup>1</sup></th>
<th>Mandatory<sup>2</sup></th>
<th>Description</th>
<th>Example</th>
</tr>
</thead>
<tbody>
<tr>
<td>key</td>
<td>Y</td>
<td>This is your unique, case-sensitive iframe public key</td>
<td>abc123</td>
</tr>
<tr>
<td>singleAmt</td>
<td>Y</td>
<td>A single amount to be charged at time of purchase</td>
<td>100.00</td>
</tr>
<!--<tr>
<td>recurAmt</td>
<td>N <sup>3</sup></td>
<td>A recurring amount to be charged</td>
<td>100.00</td>
</tr>
<tr>
<td>recurFreq</td>
<td>N <sup>3</sup></td>
<td>Frequency of recurring billing. At this time, only “m” (monthly) is available.</td>
<td>m</td>
</tr>
<tr>
<td>recurStart</td>
<td>N <sup>3</sup></td>
<td>Date to start recurring billing</td>
<td>2018-01-01 12:00:00</td>
</tr>-->
<tr>
<td>curr</td>
<td>Y</td>
<td>Destination currency of transaction (<a href="https://en.wikipedia.org/wiki/ISO_4217">ISO 4217</a>)</td>
<td>CAD</td>
</tr>
<tr>
<td>firstName</td>
<td>N</td>
<td>Customer's first name</td>
<td>John</td>
</tr>
<tr>
<td>lastName</td>
<td>N</td>
<td>Customer's last name</td>
<td>Smith</td>
</tr>
<tr>
<td>address</td>
<td>N</td>
<td>Customer's street address</td>
<td>123 Street</td>
</tr>
<tr>
<td>city</td>
<td>N</td>
<td>Customer's city</td>
<td>Toronto</td>
</tr>
<tr>
<td>region</td>
<td>N</td>
<td>Customer's state, province or other region</td>
<td>Ontario</td>
</tr>
<tr>
<td>country</td>
<td>N</td>
<td>Customer's country (<a href="https://en.wikipedia.org/wiki/ISO_4217">ISO 3166-1 alpha-2</a>)</td>
<td>CA</td>
</tr>
<tr>
<td>postalCode</td>
<td>N</td>
<td>Customer's postal code</td>
<td>A1A1A1</td>
</tr>
<tr>
<td>email<sup>4</sup></td>
<td>N</td>
<td>Customer's email address</td>
<td>john.smith@email.com</td>
</tr>
<tr>
<td>phone</td>
<td>N</td>
<td>Customer's phone number</td>
<td>555-555-5555</td>
</tr>
<tr>
<td>customConsumerID<sup>5</sup></td>
<td>N</td>
<td>Any alphanumeric ID you choose, up to a maximum of 32 characters</td>
<td></td>
</tr>
<tr>
<td>customOrderID<sup>5</sup></td>
<td>N</td>
<td>Any alphanumeric ID you choose, up to a maximum of 32 characters</td>
<td></td>
</tr>
</tbody>
</table>

<sup>1</sup> "Camelcase" has been used for visual clarity, but any case may be used when implemented.

<sup>2</sup> If mandatory input parameters aren't provided, the iframe will display an error message and fail to submit transactions.

<!--<sup>3</sup> SingleAmt and recurAmt are individually non-mandatory, but one must be used. Also, if recurAmt is used, recurFreq and recurStart both become mandatory.-->

<sup>4</sup> Email is a unique field.  This is used to determine whether two consumers are the same. 

<sup>5</sup> These fields are entirely at the retailers discretion to employ as they see fit.  It is recommended they be used to track your own ids within smartpay to make it easier to match records.
