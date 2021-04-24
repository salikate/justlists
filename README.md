# JustLists
A TRON token list standard

## What is JustLists?

JustLists is a specification for lists of token metadata (e.g. addresses, symbols or names) that can be used by a number of DApp interfaces that need one or more lists.

Anyone can create and maintain a token list on TRON by following the specification.

## Validate JustLists？

You can use ajv or other libraries to perform the validation against the JSON schema.

## Create a JustList

The best way to write a JustList is to use an editor that supports JSON schema validation. Most code editors do, such as IntelliJ and VSCode.

In order for your token list to be usable, it must pass all JSON schema validation.

## Semantic Versioning

List versions must follow the rules:

Increment major version when tokens are removed;

Increment minor version when tokens are added;

Increment patch version when tokens already on the list have minor details changed (name, symbol, logo URL, decimals).

Changing a token address or chain ID is considered both a remove and an add, and should be a major version update.

Note that list versioning is used to improve the user experience, but not for security, i.e. list versions are not meant to provide protection against malicious updates to a token list.

## Deploy your JustList

If hosted on HTTPS, make sure the endpoint is configured to send an access-control-allow-origin header to avoid CORS errors.

## Example

You can check the example below to learn how to create a list.

```
{
   "name": "TokenListExample", #List name
   "logoURI": "https://coin.top/production/upload/logo/TEe6iWDo21MRByP7ohCnXozGmq8tfCkYZY.jpeg?t=1619200677649", #List logo uri
   "timestamp": 1610339529000, #Update time in millisecond
   "tokens": [{
           "CHITA INU (CHI)": 1, #CHITA INU (CHI), which is currently 1
           "address": "TEe6iWDo21MRByP7ohCnXozGmq8tfCkYZY", #Token address
           "name": "CHITA INU (CHI)", #Token name
           "symbol": "CHI", #Token symbol
           "decimals": 8, #Token decimals
           "logoURI": "https://coin.top/production/upload/logo/TEe6iWDo21MRByP7ohCnXozGmq8tfCkYZY.jpeg?t=1619200677649" #Token logo uri
       },
       {
           "CHITA INU (CHI)": 1,
           "address": "TEe6iWDo21MRByP7ohCnXozGmq8tfCkYZY",
           "name": "CHITA INU (CHI)",
           "symbol": "CHI",
           "decimals": 18,
           "logoURI": "https://coin.top/production/upload/logo/TEe6iWDo21MRByP7ohCnXozGmq8tfCkYZY.jpeg?t=1619200677649"
       }
   ],
   "version": { #Version info
       "major": 1, #Major version
       "minor": 0, #Minor version
       "patch": 0  #Patch version
   }
}
```
