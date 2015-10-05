# tools-coreinclude
Repository that contains shared files that could be useful to both the private LCATools system and a, yet to be created, public tools repository.

### Files
* countrySelect.php - seperate file with list of countries that can be used to easily create a select box to choose country with 2 letter ISO code as select value.
* OAuth.php - OAuth related classes a libary from Mediawiki Extension:OAuth and elsewhere (MIT Andy Smith)  
* JWT.php - JSON Web Token implementantion originally a library from Mediawiki Extension:OAuth and elsewhere (http://opensource.org/licenses/BSD-3-Clause 3-clause BSD Anant Narayanan anant@php.net and Neuman Vong neuman@twilio.com)  
* MWOAuthSignatureMethod.php - extension of OAuth RSA signature method (always load OAuth.php first) for mediawiki specifically. From Mediawiki Extension:OAuth GNU General Public License 2.0
* sugar.class.php - Class for interacting with a SugarCRM installation.
* multiuseFunctions.php - file with functions used (or which could be used) in multiple different forms. Currently contains:  
  * setupdataurl() - takes a file and converts into a well formed dataurl.  
    * Accepts: input file  
    * Returns: array (kind of file, file_name, data url) Kind of file currently hardcoded to original  
  * curlAPIpost() - takes post data and headers and sends to a designated API.  
    * Accepts: url to post to, data, headers (optional)  
    * Returns: response  
  * lcalog() - Logs data to the central log for lcatools  
    * Accepts: user, log type, log title, test marker  
    * Returns: log id  
  * libxml_display_error() and libxml_display_errors() - functions from PHP documentation comments that assist in better formatting for XML verification errors (mostly used for verifying submission against xsd)  
    * Accepts: Error  
    * Returns: error information  
  * NCMECsimpleauthdcurlPost() - function for simple authenticated posts to NCMEC containing only basic form field data such as a file or report id. Used for all file submissions, to close a report and to retract a report.  
    * Accepts: username, password, post url, post data  
    * Returns: response  
  * curlauthdAPIpost() - function for more complex authenticated posts to NCMEC containing XML data, used to open reports and to submit file details after submitting a file.  
    * Accepts: username, password, post url, post data, post headers (optional)  
    * Returns: response  
  * noheaderstringget() - send a simple url get (using query string)  
    * Accepts: request (as full url)  
    * Returns: response  
  * mwOAuthAPIcall() - regular api call to MW Oauth  
    * Accepts: url, api parameters, oauth signed request (for headers)  
    * Returns: response  
  * validateJWT() - function from Chris Steipp to validate mediawiki Json Web Token  
    * Accepts: identity (web token), consumer key, nonce, server (where you got the JWT from)  
    * Response: boolean response  
	getUserData() - function to grab specific data for user from lcatools user table  
    * Accepts: User  
    * Response: Array of data from user table 
