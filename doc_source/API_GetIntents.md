# GetIntents<a name="API_GetIntents"></a>

Returns intent information as follows: 

+ If you specify the `nameContains` field, returns the `$LATEST` version of all intents that contain the specified string\.

+  If you don't specify the `nameContains` field, returns information about the `$LATEST` version of all intents\. 

 The operation requires permission for the `lex:GetIntents` action\. 

## Request Syntax<a name="API_GetIntents_RequestSyntax"></a>

```
GET /intents/?maxResults=maxResults&nameContains=nameContains&nextToken=nextToken HTTP/1.1
```

## URI Request Parameters<a name="API_GetIntents_RequestParameters"></a>

The request requires the following URI parameters\.

 ** maxResults **   
The maximum number of intents to return in the response\. The default is 10\.  
Valid Range: Minimum value of 1\. Maximum value of 50\.

 ** nameContains **   
Substring to match in intent names\. An intent will be returned if any part of its name matches the substring\. For example, "xyz" matches both "xyzabc" and "abcxyz\."  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([A-Za-z]_?)+$` 

 ** nextToken **   
A pagination token that fetches the next page of intents\. If the response to this API call is truncated, Amazon Lex returns a pagination token in the response\. To fetch the next page of intents, specify the pagination token in the next request\. 

## Request Body<a name="API_GetIntents_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_GetIntents_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "intents": [ 
      { 
         "createdDate": number,
         "description": "string",
         "lastUpdatedDate": number,
         "name": "string",
         "version": "string"
      }
   ],
   "nextToken": "string"
}
```

## Response Elements<a name="API_GetIntents_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** intents **   
An array of `Intent` objects\. For more information, see [PutBot](API_PutBot.md)\.  
Type: Array of [IntentMetadata](API_IntentMetadata.md) objects

 ** nextToken **   
If the response is truncated, the response includes a pagination token that you can specify in your next request to fetch the next page of intents\.   
Type: String

## Errors<a name="API_GetIntents_Errors"></a>

 **BadRequestException**   
The request is not well formed\. For example, a value is invalid or a required field is missing\. Check the field values, and try again\.  
HTTP Status Code: 400

 **InternalFailureException**   
An internal Amazon Lex error occurred\. Try your request again\.  
HTTP Status Code: 500

 **LimitExceededException**   
The request exceeded a limit\. Try your request again\.  
HTTP Status Code: 429

 **NotFoundException**   
The resource specified in the request was not found\. Check the resource and try again\.  
HTTP Status Code: 404

## See Also<a name="API_GetIntents_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:

+  [AWS Command Line Interface](http://docs.aws.amazon.com/goto/aws-cli/lex-models-2017-04-19/GetIntents) 

+  [AWS SDK for \.NET](http://docs.aws.amazon.com/goto/DotNetSDKV3/lex-models-2017-04-19/GetIntents) 

+  [AWS SDK for C\+\+](http://docs.aws.amazon.com/goto/SdkForCpp/lex-models-2017-04-19/GetIntents) 

+  [AWS SDK for Go](http://docs.aws.amazon.com/goto/SdkForGoV1/lex-models-2017-04-19/GetIntents) 

+  [AWS SDK for Java](http://docs.aws.amazon.com/goto/SdkForJava/lex-models-2017-04-19/GetIntents) 

+  [AWS SDK for JavaScript](http://docs.aws.amazon.com/goto/AWSJavaScriptSDK/lex-models-2017-04-19/GetIntents) 

+  [AWS SDK for PHP V3](http://docs.aws.amazon.com/goto/SdkForPHPV3/lex-models-2017-04-19/GetIntents) 

+  [AWS SDK for Python](http://docs.aws.amazon.com/goto/boto3/lex-models-2017-04-19/GetIntents) 

+  [AWS SDK for Ruby V2](http://docs.aws.amazon.com/goto/SdkForRubyV2/lex-models-2017-04-19/GetIntents) 