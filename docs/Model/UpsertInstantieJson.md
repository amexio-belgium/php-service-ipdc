# # UpsertInstantieJson

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **object** |  | [optional]
**bevoegd_bestuursniveaus** | **object[]** |  | [optional]
**uitvoerend_bestuursniveaus** | **object[]** |  | [optional]
**naam** | [**\OpenAPI\Client\Model\InputVertalingen**](InputVertalingen.md) |  |
**beschrijving** | [**\OpenAPI\Client\Model\InputVertalingen**](InputVertalingen.md) |  |
**verdere_beschrijving** | [**\OpenAPI\Client\Model\InputVertalingen**](InputVertalingen.md) |  | [optional]
**start_dienst_verlening** | **\DateTime** |  | [optional]
**einde_dienst_verlening** | **\DateTime** |  | [optional]
**publicatiekanalen** | **object[]** |  | [optional]
**tags** | **object[]** |  | [optional]
**type** | **object** |  | [optional]
**themas** | **object[]** |  | [optional]
**doelgroepen** | **object[]** |  | [optional]
**talen** | **object[]** |  | [optional]
**geografisch_toepassingsgebieden** | **object[]** |  |
**your_europe_categorieen** | **object[]** |  | [optional]
**regelgeving_tekst** | [**\OpenAPI\Client\Model\InputVertalingen**](InputVertalingen.md) |  | [optional]
**uitzonderingen** | [**\OpenAPI\Client\Model\InputVertalingen**](InputVertalingen.md) |  | [optional]
**zoektermen** | [**\OpenAPI\Client\Model\InputVertalingen**](InputVertalingen.md) |  | [optional]
**aangemaakt_door** | [**\OpenAPI\Client\Model\PubliekeOrganisatie**](PubliekeOrganisatie.md) |  | [optional]
**bevoegde_overheden** | [**\OpenAPI\Client\Model\PubliekeOrganisatie[]**](PubliekeOrganisatie.md) |  |
**uitvoerende_overheden** | [**\OpenAPI\Client\Model\PubliekeOrganisatie[]**](PubliekeOrganisatie.md) |  | [optional]
**contact_overheden** | [**\OpenAPI\Client\Model\ContactOrganisatie[]**](ContactOrganisatie.md) |  | [optional]
**contact_beschrijving** | [**\OpenAPI\Client\Model\InputVertalingen**](InputVertalingen.md) |  | [optional]
**voorwaarden** | [**\OpenAPI\Client\Model\ShaclOrderedUpsertVoorwaarde[]**](ShaclOrderedUpsertVoorwaarde.md) |  | [optional]
**procedures** | [**\OpenAPI\Client\Model\ShaclOrderedUpsertProcedureJson[]**](ShaclOrderedUpsertProcedureJson.md) |  | [optional]
**websites** | [**\OpenAPI\Client\Model\ShaclOrderedUpsertWebsite[]**](ShaclOrderedUpsertWebsite.md) |  | [optional]
**kosten** | [**\OpenAPI\Client\Model\ShaclOrderedUpsertKost[]**](ShaclOrderedUpsertKost.md) |  | [optional]
**financiele_voordelen** | [**\OpenAPI\Client\Model\ShaclOrderedUpsertFinancieelVoordeel[]**](ShaclOrderedUpsertFinancieelVoordeel.md) |  | [optional]
**regelgeving** | [**\OpenAPI\Client\Model\ShaclOrderedUpsertRegelgeving[]**](ShaclOrderedUpsertRegelgeving.md) |  | [optional]
**contactgegevens** | [**\OpenAPI\Client\Model\ShaclOrderedUpsertContactgegevens[]**](ShaclOrderedUpsertContactgegevens.md) |  | [optional]
**linked_concept** | **object** |  | [optional]
**subsidiemaatregel** | **string** |  | [optional]
**publicatie_link** | [**\OpenAPI\Client\Model\Website**](Website.md) |  | [optional]
**verwante_producten** | [**\OpenAPI\Client\Model\ShaclOrderedUpsertVerwantProductJson[]**](ShaclOrderedUpsertVerwantProductJson.md) |  | [optional]
**deminimis** | **bool** |  | [optional]
**creatie** | **\DateTime** |  | [optional]
**laatst_gewijzigd** | **\DateTime** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
