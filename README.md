## Introduction
OAuth helper class in PHP

## Usage
1. You can extends oauth_helper to add specific functions, such as twitter extends oauth_helper
2. Call request_token method to get oauth_token and oauth_token_secret, and redirect user to authorize_url, developer needs to store oauth_token and oauth_token_secret somewhere, we will use them to request access token later on
3. User approved the request, and get back to moodle
4. Call get_access_token, it takes previous oauth_token and oauth_token_secret as arguments, oauth_token will be used in OAuth request, oauth_token_secret will be used to bulid signature, this method will return access_token and access_secret, store these two values in database or session
5. Now you can access oauth protected resources by access_token and access_secret using oauth_helper::request method (or get() post())
 	 	 	

## Note:
- This class only support HMAC-SHA1
- oauth_helper class don't store tokens and secrets, you must store them manually
- Some functions are based on http://code.google.com/p/oauth/

## copyright
2010 Dongsheng Cai {@link http://dongsheng.org}

##license
http://www.gnu.org/copyleft/gpl.html GNU GPL v3 or later
