[![NuGet](https://img.shields.io/badge/nuget-v2.4.2-green.svg?style=flat)](https://www.nuget.org/packages/IBM.WatsonDeveloperCloud.LanguageTranslator.v2/)

### Language Translator V2
**Language Translator v3 is now available. The v2 Language Translator API will no longer be available after July 31, 2018. To take advantage of the latest service enhancements, migrate to the v3 API. View the [Migrating to Language Translator v3](https://console.bluemix.net/docs/services/language-translator/migrating.html) page for more information.**

[Language Translator][language_translator] translates text from one language to another. The service offers multiple domain-specific models that you can customize based on your unique terminology and language. Use Language Translator to take news from across the globe and present it in your language, communicate with your customers in their own language, and more.

### Installation
#### Nuget
```

PM > Install-Package IBM.WatsonDeveloperCloud.LanguageTranslator.v2

```
#### .csproj
```xml

<ItemGroup>
    <PackageReference Include="IBM.WatsonDeveloperCloud.LanguageTranslator.v2" Version="2.4.2" />
</ItemGroup>

```
### Usage
Select a domain, then identify or select the language of text, and then translate the text from one supported language to another.

#### Translate
Translates input text from the source language to the target language.
```cs
// Translate '"Hello! How are you?' from English to Portuguese using the Language Translator service
var results = _languageTranslator.Translate("en", "pt", "Hello! How are you?");
```

#### Identifiable languages
Return the list of languages it can detect.
```cs
//  returns a list of identifiable languages
var result = _languageTranslator.GetIdentifiableLanguages();
```

#### Identify language
Identify the language in which a text is written.
```cs
//  identifies the language of a body of text.
var result = _languageTranslator.Identify("<text-to-identify>");
```

#### List models
Lists available models for language translation with option to filter by source or by target language.
```cs
//  lists all language models
var result = _languageTranslator.ListModels();
```

<!-- #### Create a model
Uploads a TMX glossary file on top of a domain to customize a translation model.Depending on the size of the file, training can range from minutes for a glossary to several hours for a large parallel corpus. Glossary files must be less than 10 MB. The cumulative file size of all uploaded glossary and corpus files is limited to 250 MB.
```cs
``` -->

#### Delete a model
Deletes trained translation models.
```cs
//  deletes a custom languge model
var result = _languageTranslator.DeleteModel("<custom-model-id>");
```

#### Get a model details
Returns information, including training status, about a specified translation model.
```cs
//  gets details of a particular model
var result = _languageTranslator.GetModelDetails("<model-id>");
```

[language_translator]: https://console.bluemix.net/docs/services/language-translator/getting-started.html
