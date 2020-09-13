# Cloudmersive.APIClient.NETCore.Currency - the C# library for the currencyapi

The currency APIs help you retrieve exchange rates and convert prices between currencies easily.

This C# SDK is for the [Cloudmersive Currency API](https://www.cloudmersive.com/currency-api):

- API version: v1
- SDK version: 2.0.1
- Build package: io.swagger.codegen.languages.CSharpClientCodegen

<a name="frameworks-supported"></a>
## Frameworks supported
- .NET Core >=1.0
- .NET Framework >=4.6
- Mono/Xamarin >=vNext
- UWP >=10.0

<a name="dependencies"></a>
## Dependencies
- FubarCoder.RestSharp.Portable.Core >=4.0.7
- FubarCoder.RestSharp.Portable.HttpClient >=4.0.7
- Newtonsoft.Json >=10.0.3

<a name="installation"></a>
## Installation
Generate the DLL using your preferred tool

Then include the DLL (under the `bin` folder) in the C# project, and use the namespaces:
```csharp
using Cloudmersive.APIClient.NETCore.Currency.Api;
using Cloudmersive.APIClient.NETCore.Currency.Client;
using Cloudmersive.APIClient.NETCore.Currency.Model;
```
<a name="getting-started"></a>
## Getting Started

```csharp
using System;
using System.Diagnostics;
using Cloudmersive.APIClient.NETCore.Currency.Api;
using Cloudmersive.APIClient.NETCore.Currency.Client;
using Cloudmersive.APIClient.NETCore.Currency.Model;

namespace Example
{
    public class Example
    {
        public void main()
        {

            // Configure API key authorization: Apikey
            Configuration.Default.ApiKey.Add("Apikey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // Configuration.Default.ApiKeyPrefix.Add("Apikey", "Bearer");

            var apiInstance = new CurrencyExchangeApi();
            var source = source_example;  // string | Source currency three-digit code (ISO 4217), e.g. USD, EUR, etc.
            var destination = destination_example;  // string | Destination currency three-digit code (ISO 4217), e.g. USD, EUR, etc.
            var sourcePrice = 1.2;  // double? | Input price, such as 19.99 in source currency

            try
            {
                // Converts a price from the source currency into the destination currency
                ConvertedCurrencyResult result = apiInstance.CurrencyExchangeConvertCurrency(source, destination, sourcePrice);
                Debug.WriteLine(result);
            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling CurrencyExchangeApi.CurrencyExchangeConvertCurrency: " + e.Message );
            }

        }
    }
}
```

<a name="documentation-for-api-endpoints"></a>
## Documentation for API Endpoints

All URIs are relative to *https://api.cloudmersive.com*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*CurrencyExchangeApi* | [**CurrencyExchangeConvertCurrency**](docs/CurrencyExchangeApi.md#currencyexchangeconvertcurrency) | **POST** /currency/exchange-rates/convert/{source}/to/{destination} | Converts a price from the source currency into the destination currency
*CurrencyExchangeApi* | [**CurrencyExchangeGetAvailableCurrencies**](docs/CurrencyExchangeApi.md#currencyexchangegetavailablecurrencies) | **POST** /currency/exchange-rates/list-available | Get a list of available currencies and corresponding countries
*CurrencyExchangeApi* | [**CurrencyExchangeGetExchangeRate**](docs/CurrencyExchangeApi.md#currencyexchangegetexchangerate) | **POST** /currency/exchange-rates/get/{source}/to/{destination} | Gets the exchange rate from the source currency into the destination currency


<a name="documentation-for-models"></a>
## Documentation for Models

 - [Model.AvailableCurrency](docs/AvailableCurrency.md)
 - [Model.AvailableCurrencyResponse](docs/AvailableCurrencyResponse.md)
 - [Model.ConvertedCurrencyResult](docs/ConvertedCurrencyResult.md)
 - [Model.ExchangeRateResult](docs/ExchangeRateResult.md)


<a name="documentation-for-authorization"></a>
## Documentation for Authorization

<a name="Apikey"></a>
### Apikey

- **Type**: API key
- **API key parameter name**: Apikey
- **Location**: HTTP header

