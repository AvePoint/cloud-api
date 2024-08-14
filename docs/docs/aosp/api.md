# Open Api

> Version v1.1

Open Api HTTP API v1.1

## Path Table

| Method | Path | Description |
| --- | --- | --- |
| GET | [/api/V1.1/Customers](#getapiv11customers) |  |
| GET | [/api/V1.1/Customers({id})](#getapiv11customersid) |  |
| GET | [/api/V1.1/Customers({Id})/Jobs](#getapiv11customersidjobs) |  |
| GET | [/api/V1.1/Customers({Id})/Jobs(JobType={JobType},JobModule={JobModule})](#getapiv11customersidjobsjobtypejobtypejobmodulejobmodule) |  |
| GET | [/api/V1.1/Customers({id})/Protected](#getapiv11customersidprotected) |  |
| GET | [/api/V1.1/Customers({id})/ScanProfiles](#getapiv11customersidscanprofiles) |  |
| GET | [/api/V1.1/Customers({id})/ScanProfilesDailyNew(ProfileId={ProfileId})](#getapiv11customersidscanprofilesdailynewprofileidprofileid) |  |
| GET | [/api/V1.1/Customers({id})/ScanProfilesDailyNewDetail(ProfileId={ProfileId})](#getapiv11customersidscanprofilesdailynewdetailprofileidprofileid) |  |
| GET | [/api/V1.1/Customers({id})/ScanProfilesDetails(ProfileId={ProfileId})](#getapiv11customersidscanprofilesdetailsprofileidprofileid) |  |
| GET | [/api/V1.1/Services](#getapiv11services) |  |
| GET | [/api/V1.1/Services({id})](#getapiv11servicesid) |  |

## Reference Table

| Name | Path | Description |
| --- | --- | --- |
| Microsoft.OData.Edm.EdmContainerElementKind | [#/components/schemas/Microsoft.OData.Edm.EdmContainerElementKind](#componentsschemasmicrosoftodataedmedmcontainerelementkind) | * `None` = 0
* `EntitySet` = 1
* `ActionImport` = 2
* `FunctionImport` = 3
* `Singleton` = 4
 |
| Microsoft.OData.Edm.EdmExpressionKind | [#/components/schemas/Microsoft.OData.Edm.EdmExpressionKind](#componentsschemasmicrosoftodataedmedmexpressionkind) | * `None` = 0
* `BinaryConstant` = 1
* `BooleanConstant` = 2
* `DateTimeOffsetConstant` = 3
* `DecimalConstant` = 4
* `FloatingConstant` = 5
* `GuidConstant` = 6
* `IntegerConstant` = 7
* `StringConstant` = 8
* `DurationConstant` = 9
* `Null` = 10
* `Record` = 11
* `Collection` = 12
* `Path` = 13
* `If` = 14
* `Cast` = 15
* `IsType` = 16
* `FunctionApplication` = 17
* `LabeledExpressionReference` = 18
* `Labeled` = 19
* `PropertyPath` = 20
* `NavigationPropertyPath` = 21
* `DateConstant` = 22
* `TimeOfDayConstant` = 23
* `EnumMember` = 24
* `AnnotationPath` = 25
 |
| Microsoft.OData.Edm.EdmSchemaElementKind | [#/components/schemas/Microsoft.OData.Edm.EdmSchemaElementKind](#componentsschemasmicrosoftodataedmedmschemaelementkind) | * `None` = 0
* `TypeDefinition` = 1
* `Term` = 2
* `Action` = 3
* `EntityContainer` = 4
* `Function` = 5
 |
| Microsoft.OData.Edm.EdmTypeKind | [#/components/schemas/Microsoft.OData.Edm.EdmTypeKind](#componentsschemasmicrosoftodataedmedmtypekind) | * `None` = 0
* `Primitive` = 1
* `Entity` = 2
* `Complex` = 3
* `Collection` = 4
* `EntityReference` = 5
* `Enum` = 6
* `TypeDefinition` = 7
* `Untyped` = 8
* `Path` = 9
 |
| Microsoft.OData.Edm.IEdmEntityContainer | [#/components/schemas/Microsoft.OData.Edm.IEdmEntityContainer](#componentsschemasmicrosoftodataedmiedmentitycontainer) |  |
| Microsoft.OData.Edm.IEdmEntityContainerElement | [#/components/schemas/Microsoft.OData.Edm.IEdmEntityContainerElement](#componentsschemasmicrosoftodataedmiedmentitycontainerelement) |  |
| Microsoft.OData.Edm.IEdmExpression | [#/components/schemas/Microsoft.OData.Edm.IEdmExpression](#componentsschemasmicrosoftodataedmiedmexpression) |  |
| Microsoft.OData.Edm.IEdmModel | [#/components/schemas/Microsoft.OData.Edm.IEdmModel](#componentsschemasmicrosoftodataedmiedmmodel) |  |
| Microsoft.OData.Edm.IEdmSchemaElement | [#/components/schemas/Microsoft.OData.Edm.IEdmSchemaElement](#componentsschemasmicrosoftodataedmiedmschemaelement) |  |
| Microsoft.OData.Edm.IEdmType | [#/components/schemas/Microsoft.OData.Edm.IEdmType](#componentsschemasmicrosoftodataedmiedmtype) |  |
| Microsoft.OData.Edm.IEdmTypeReference | [#/components/schemas/Microsoft.OData.Edm.IEdmTypeReference](#componentsschemasmicrosoftodataedmiedmtypereference) |  |
| Microsoft.OData.Edm.Vocabularies.IEdmDirectValueAnnotationsManager | [#/components/schemas/Microsoft.OData.Edm.Vocabularies.IEdmDirectValueAnnotationsManager](#componentsschemasmicrosoftodataedmvocabulariesiedmdirectvalueannotationsmanager) |  |
| Microsoft.OData.Edm.Vocabularies.IEdmTerm | [#/components/schemas/Microsoft.OData.Edm.Vocabularies.IEdmTerm](#componentsschemasmicrosoftodataedmvocabulariesiedmterm) |  |
| Microsoft.OData.Edm.Vocabularies.IEdmVocabularyAnnotatable | [#/components/schemas/Microsoft.OData.Edm.Vocabularies.IEdmVocabularyAnnotatable](#componentsschemasmicrosoftodataedmvocabulariesiedmvocabularyannotatable) |  |
| Microsoft.OData.Edm.Vocabularies.IEdmVocabularyAnnotation | [#/components/schemas/Microsoft.OData.Edm.Vocabularies.IEdmVocabularyAnnotation](#componentsschemasmicrosoftodataedmvocabulariesiedmvocabularyannotation) |  |
| Microsoft.OData.ODataEntitySetInfo | [#/components/schemas/Microsoft.OData.ODataEntitySetInfo](#componentsschemasmicrosoftodataodataentitysetinfo) |  |
| Microsoft.OData.ODataFunctionImportInfo | [#/components/schemas/Microsoft.OData.ODataFunctionImportInfo](#componentsschemasmicrosoftodataodatafunctionimportinfo) |  |
| Microsoft.OData.ODataServiceDocument | [#/components/schemas/Microsoft.OData.ODataServiceDocument](#componentsschemasmicrosoftodataodataservicedocument) |  |
| Microsoft.OData.ODataSingletonInfo | [#/components/schemas/Microsoft.OData.ODataSingletonInfo](#componentsschemasmicrosoftodataodatasingletoninfo) |  |
| Microsoft.OData.ODataTypeAnnotation | [#/components/schemas/Microsoft.OData.ODataTypeAnnotation](#componentsschemasmicrosoftodataodatatypeannotation) |  |
| Bearer | [#/components/securitySchemes/Bearer](#componentssecurityschemesbearer) | JWT Authorization header using the Bearer scheme. |

## Path Details

***

### [GET]/api/V1.1/Customers

- Description  
Get the general information of the customers that you manage.

#### Responses

- 200 OK

***

### [GET]/api/V1.1/Customers({id})

- Description  
Get the general information of a specific customer that you manage.

#### Responses

- 200 OK

***

### [GET]/api/V1.1/Customers({Id})/Jobs

- Description  
Get the job details of the backup services of a specific customer that you manage.

#### Parameters(Query)

```ts
JobType?: string
```

```ts
JobModule?: string
```

#### Responses

- 200 OK

***

### [GET]/api/V1.1/Customers({Id})/Jobs(JobType={JobType},JobModule={JobModule})

- Description  
Get the job details of a specific job type and module of backup service for a customer that you manage.

#### Parameters(Query)

```ts
JobType?: string
```

```ts
JobModule?: string
```

#### Responses

- 200 OK

***

### [GET]/api/V1.1/Customers({id})/Protected

- Description  
Get your customers’ protected data information of Cloud Backup for Microsoft 365. 

#### Responses

- 200 OK

***

### [GET]/api/V1.1/Customers({id})/ScanProfiles

- Description  
Get the information of all scan profiles configured in AvePoint Online Services for a customer.

#### Responses

- 200 OK

***

### [GET]/api/V1.1/Customers({id})/ScanProfilesDailyNew(ProfileId={ProfileId})

- Description  
Get the daily scan profile changes in AvePoint Online Services for a customer.

#### Responses

- 200 OK

***

### [GET]/api/V1.1/Customers({id})/ScanProfilesDailyNewDetail(ProfileId={ProfileId})

- Description  
Get the daily scan profile change details in AvePoint Online Services for a customer.

#### Responses

- 200 OK

***

### [GET]/api/V1.1/Customers({id})/ScanProfilesDetails(ProfileId={ProfileId})

- Description  
Get a scan profile information configured in AvePoint Online Services for a customer.

#### Responses

- 200 OK

***

### [GET]/api/V1.1/Services

- Description  
Get the license details of different services for the customers that you manage.

#### Parameters(Query)

```ts
id?: string
```

#### Responses

- 200 OK

***

### [GET]/api/V1.1/Services({id})

- Description  
Get the license details of different services for a specific customer that you manage.

#### Responses

- 200 OK

## References

### #/components/schemas/Microsoft.OData.Edm.EdmContainerElementKind

```ts
{
  "enum": [
    0,
    1,
    2,
    3,
    4
  ],
  "type": "integer",
  "description": "* `None` = 0\r\n* `EntitySet` = 1\r\n* `ActionImport` = 2\r\n* `FunctionImport` = 3\r\n* `Singleton` = 4\r\n",
  "format": "int32"
}
```

### #/components/schemas/Microsoft.OData.Edm.EdmExpressionKind

```ts
{
  "enum": [
    0,
    1,
    2,
    3,
    4,
    5,
    6,
    7,
    8,
    9,
    10,
    11,
    12,
    13,
    14,
    15,
    16,
    17,
    18,
    19,
    20,
    21,
    22,
    23,
    24,
    25
  ],
  "type": "integer",
  "description": "* `None` = 0\r\n* `BinaryConstant` = 1\r\n* `BooleanConstant` = 2\r\n* `DateTimeOffsetConstant` = 3\r\n* `DecimalConstant` = 4\r\n* `FloatingConstant` = 5\r\n* `GuidConstant` = 6\r\n* `IntegerConstant` = 7\r\n* `StringConstant` = 8\r\n* `DurationConstant` = 9\r\n* `Null` = 10\r\n* `Record` = 11\r\n* `Collection` = 12\r\n* `Path` = 13\r\n* `If` = 14\r\n* `Cast` = 15\r\n* `IsType` = 16\r\n* `FunctionApplication` = 17\r\n* `LabeledExpressionReference` = 18\r\n* `Labeled` = 19\r\n* `PropertyPath` = 20\r\n* `NavigationPropertyPath` = 21\r\n* `DateConstant` = 22\r\n* `TimeOfDayConstant` = 23\r\n* `EnumMember` = 24\r\n* `AnnotationPath` = 25\r\n",
  "format": "int32"
}
```

### #/components/schemas/Microsoft.OData.Edm.EdmSchemaElementKind

```ts
{
  "enum": [
    0,
    1,
    2,
    3,
    4,
    5
  ],
  "type": "integer",
  "description": "* `None` = 0\r\n* `TypeDefinition` = 1\r\n* `Term` = 2\r\n* `Action` = 3\r\n* `EntityContainer` = 4\r\n* `Function` = 5\r\n",
  "format": "int32"
}
```

### #/components/schemas/Microsoft.OData.Edm.EdmTypeKind

```ts
{
  "enum": [
    0,
    1,
    2,
    3,
    4,
    5,
    6,
    7,
    8,
    9
  ],
  "type": "integer",
  "description": "* `None` = 0\r\n* `Primitive` = 1\r\n* `Entity` = 2\r\n* `Complex` = 3\r\n* `Collection` = 4\r\n* `EntityReference` = 5\r\n* `Enum` = 6\r\n* `TypeDefinition` = 7\r\n* `Untyped` = 8\r\n* `Path` = 9\r\n",
  "format": "int32"
}
```

### #/components/schemas/Microsoft.OData.Edm.IEdmEntityContainer

```ts
{
  elements: {
    // * `None` = 0
    // * `EntitySet` = 1
    // * `ActionImport` = 2
    // * `FunctionImport` = 3
    // * `Singleton` = 4
    // 
    containerElementKind?: enum[0, 1, 2, 3, 4]
    container: {
      elements:#/components/schemas/Microsoft.OData.Edm.IEdmEntityContainerElement[]
      // * `None` = 0
      // * `TypeDefinition` = 1
      // * `Term` = 2
      // * `Action` = 3
      // * `EntityContainer` = 4
      // * `Function` = 5
      // 
      schemaElementKind?: enum[0, 1, 2, 3, 4, 5]
      namespace?: string
      name?: string
    }
    name?: string
  }[]
  schemaElementKind:#/components/schemas/Microsoft.OData.Edm.EdmSchemaElementKind
  namespace?: string
  name?: string
}
```

### #/components/schemas/Microsoft.OData.Edm.IEdmEntityContainerElement

```ts
{
  // * `None` = 0
  // * `EntitySet` = 1
  // * `ActionImport` = 2
  // * `FunctionImport` = 3
  // * `Singleton` = 4
  // 
  containerElementKind?: enum[0, 1, 2, 3, 4]
  container: {
    elements: {
      containerElementKind:#/components/schemas/Microsoft.OData.Edm.EdmContainerElementKind
      container:#/components/schemas/Microsoft.OData.Edm.IEdmEntityContainer
      name?: string
    }[]
    // * `None` = 0
    // * `TypeDefinition` = 1
    // * `Term` = 2
    // * `Action` = 3
    // * `EntityContainer` = 4
    // * `Function` = 5
    // 
    schemaElementKind?: enum[0, 1, 2, 3, 4, 5]
    namespace?: string
    name?: string
  }
  name?: string
}
```

### #/components/schemas/Microsoft.OData.Edm.IEdmExpression

```ts
{
  // * `None` = 0
  // * `BinaryConstant` = 1
  // * `BooleanConstant` = 2
  // * `DateTimeOffsetConstant` = 3
  // * `DecimalConstant` = 4
  // * `FloatingConstant` = 5
  // * `GuidConstant` = 6
  // * `IntegerConstant` = 7
  // * `StringConstant` = 8
  // * `DurationConstant` = 9
  // * `Null` = 10
  // * `Record` = 11
  // * `Collection` = 12
  // * `Path` = 13
  // * `If` = 14
  // * `Cast` = 15
  // * `IsType` = 16
  // * `FunctionApplication` = 17
  // * `LabeledExpressionReference` = 18
  // * `Labeled` = 19
  // * `PropertyPath` = 20
  // * `NavigationPropertyPath` = 21
  // * `DateConstant` = 22
  // * `TimeOfDayConstant` = 23
  // * `EnumMember` = 24
  // * `AnnotationPath` = 25
  // 
  expressionKind?: enum[0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25]
}
```

### #/components/schemas/Microsoft.OData.Edm.IEdmModel

```ts
{
  schemaElements: {
    // * `None` = 0
    // * `TypeDefinition` = 1
    // * `Term` = 2
    // * `Action` = 3
    // * `EntityContainer` = 4
    // * `Function` = 5
    // 
    schemaElementKind?: enum[0, 1, 2, 3, 4, 5]
    namespace?: string
    name?: string
  }[]
  vocabularyAnnotations: {
    qualifier?: string
    term: {
      type: {
        isNullable?: boolean
        definition: {
          // * `None` = 0
          // * `Primitive` = 1
          // * `Entity` = 2
          // * `Complex` = 3
          // * `Collection` = 4
          // * `EntityReference` = 5
          // * `Enum` = 6
          // * `TypeDefinition` = 7
          // * `Untyped` = 8
          // * `Path` = 9
          // 
          typeKind?: enum[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
        }
      }
      appliesTo?: string
      defaultValue?: string
      schemaElementKind:#/components/schemas/Microsoft.OData.Edm.EdmSchemaElementKind
      namespace?: string
      name?: string
    }
    target: {
    }
    value: {
      // * `None` = 0
      // * `BinaryConstant` = 1
      // * `BooleanConstant` = 2
      // * `DateTimeOffsetConstant` = 3
      // * `DecimalConstant` = 4
      // * `FloatingConstant` = 5
      // * `GuidConstant` = 6
      // * `IntegerConstant` = 7
      // * `StringConstant` = 8
      // * `DurationConstant` = 9
      // * `Null` = 10
      // * `Record` = 11
      // * `Collection` = 12
      // * `Path` = 13
      // * `If` = 14
      // * `Cast` = 15
      // * `IsType` = 16
      // * `FunctionApplication` = 17
      // * `LabeledExpressionReference` = 18
      // * `Labeled` = 19
      // * `PropertyPath` = 20
      // * `NavigationPropertyPath` = 21
      // * `DateConstant` = 22
      // * `TimeOfDayConstant` = 23
      // * `EnumMember` = 24
      // * `AnnotationPath` = 25
      // 
      expressionKind?: enum[0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25]
    }
  }[]
  referencedModels: {
    schemaElements:#/components/schemas/Microsoft.OData.Edm.IEdmSchemaElement[]
    vocabularyAnnotations:#/components/schemas/Microsoft.OData.Edm.Vocabularies.IEdmVocabularyAnnotation[]
    referencedModels:#/components/schemas/Microsoft.OData.Edm.IEdmModel[]
    declaredNamespaces?: string[]
    directValueAnnotationsManager: {
    }
    entityContainer: {
      elements: {
        // * `None` = 0
        // * `EntitySet` = 1
        // * `ActionImport` = 2
        // * `FunctionImport` = 3
        // * `Singleton` = 4
        // 
        containerElementKind?: enum[0, 1, 2, 3, 4]
        container:#/components/schemas/Microsoft.OData.Edm.IEdmEntityContainer
        name?: string
      }[]
      schemaElementKind:#/components/schemas/Microsoft.OData.Edm.EdmSchemaElementKind
      namespace?: string
      name?: string
    }
  }[]
  declaredNamespaces?: string[]
  directValueAnnotationsManager:#/components/schemas/Microsoft.OData.Edm.Vocabularies.IEdmDirectValueAnnotationsManager
  entityContainer:#/components/schemas/Microsoft.OData.Edm.IEdmEntityContainer
}
```

### #/components/schemas/Microsoft.OData.Edm.IEdmSchemaElement

```ts
{
  // * `None` = 0
  // * `TypeDefinition` = 1
  // * `Term` = 2
  // * `Action` = 3
  // * `EntityContainer` = 4
  // * `Function` = 5
  // 
  schemaElementKind?: enum[0, 1, 2, 3, 4, 5]
  namespace?: string
  name?: string
}
```

### #/components/schemas/Microsoft.OData.Edm.IEdmType

```ts
{
  // * `None` = 0
  // * `Primitive` = 1
  // * `Entity` = 2
  // * `Complex` = 3
  // * `Collection` = 4
  // * `EntityReference` = 5
  // * `Enum` = 6
  // * `TypeDefinition` = 7
  // * `Untyped` = 8
  // * `Path` = 9
  // 
  typeKind?: enum[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
}
```

### #/components/schemas/Microsoft.OData.Edm.IEdmTypeReference

```ts
{
  isNullable?: boolean
  definition: {
    // * `None` = 0
    // * `Primitive` = 1
    // * `Entity` = 2
    // * `Complex` = 3
    // * `Collection` = 4
    // * `EntityReference` = 5
    // * `Enum` = 6
    // * `TypeDefinition` = 7
    // * `Untyped` = 8
    // * `Path` = 9
    // 
    typeKind?: enum[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
  }
}
```

### #/components/schemas/Microsoft.OData.Edm.Vocabularies.IEdmDirectValueAnnotationsManager

```ts
{
}
```

### #/components/schemas/Microsoft.OData.Edm.Vocabularies.IEdmTerm

```ts
{
  type: {
    isNullable?: boolean
    definition: {
      // * `None` = 0
      // * `Primitive` = 1
      // * `Entity` = 2
      // * `Complex` = 3
      // * `Collection` = 4
      // * `EntityReference` = 5
      // * `Enum` = 6
      // * `TypeDefinition` = 7
      // * `Untyped` = 8
      // * `Path` = 9
      // 
      typeKind?: enum[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    }
  }
  appliesTo?: string
  defaultValue?: string
  // * `None` = 0
  // * `TypeDefinition` = 1
  // * `Term` = 2
  // * `Action` = 3
  // * `EntityContainer` = 4
  // * `Function` = 5
  // 
  schemaElementKind?: enum[0, 1, 2, 3, 4, 5]
  namespace?: string
  name?: string
}
```

### #/components/schemas/Microsoft.OData.Edm.Vocabularies.IEdmVocabularyAnnotatable

```ts
{
}
```

### #/components/schemas/Microsoft.OData.Edm.Vocabularies.IEdmVocabularyAnnotation

```ts
{
  qualifier?: string
  term: {
    type: {
      isNullable?: boolean
      definition: {
        // * `None` = 0
        // * `Primitive` = 1
        // * `Entity` = 2
        // * `Complex` = 3
        // * `Collection` = 4
        // * `EntityReference` = 5
        // * `Enum` = 6
        // * `TypeDefinition` = 7
        // * `Untyped` = 8
        // * `Path` = 9
        // 
        typeKind?: enum[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
      }
    }
    appliesTo?: string
    defaultValue?: string
    // * `None` = 0
    // * `TypeDefinition` = 1
    // * `Term` = 2
    // * `Action` = 3
    // * `EntityContainer` = 4
    // * `Function` = 5
    // 
    schemaElementKind?: enum[0, 1, 2, 3, 4, 5]
    namespace?: string
    name?: string
  }
  target: {
  }
  value: {
    // * `None` = 0
    // * `BinaryConstant` = 1
    // * `BooleanConstant` = 2
    // * `DateTimeOffsetConstant` = 3
    // * `DecimalConstant` = 4
    // * `FloatingConstant` = 5
    // * `GuidConstant` = 6
    // * `IntegerConstant` = 7
    // * `StringConstant` = 8
    // * `DurationConstant` = 9
    // * `Null` = 10
    // * `Record` = 11
    // * `Collection` = 12
    // * `Path` = 13
    // * `If` = 14
    // * `Cast` = 15
    // * `IsType` = 16
    // * `FunctionApplication` = 17
    // * `LabeledExpressionReference` = 18
    // * `Labeled` = 19
    // * `PropertyPath` = 20
    // * `NavigationPropertyPath` = 21
    // * `DateConstant` = 22
    // * `TimeOfDayConstant` = 23
    // * `EnumMember` = 24
    // * `AnnotationPath` = 25
    // 
    expressionKind?: enum[0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25]
  }
}
```

### #/components/schemas/Microsoft.OData.ODataEntitySetInfo

```ts
{
  url?: string
  name?: string
  title?: string
  typeAnnotation: {
    typeName?: string
  }
}
```

### #/components/schemas/Microsoft.OData.ODataFunctionImportInfo

```ts
{
  url?: string
  name?: string
  title?: string
  typeAnnotation: {
    typeName?: string
  }
}
```

### #/components/schemas/Microsoft.OData.ODataServiceDocument

```ts
{
  entitySets: {
    url?: string
    name?: string
    title?: string
    typeAnnotation: {
      typeName?: string
    }
  }[]
  singletons: {
    url?: string
    name?: string
    title?: string
    typeAnnotation:#/components/schemas/Microsoft.OData.ODataTypeAnnotation
  }[]
  functionImports: {
    url?: string
    name?: string
    title?: string
    typeAnnotation:#/components/schemas/Microsoft.OData.ODataTypeAnnotation
  }[]
  typeAnnotation:#/components/schemas/Microsoft.OData.ODataTypeAnnotation
}
```

### #/components/schemas/Microsoft.OData.ODataSingletonInfo

```ts
{
  url?: string
  name?: string
  title?: string
  typeAnnotation: {
    typeName?: string
  }
}
```

### #/components/schemas/Microsoft.OData.ODataTypeAnnotation

```ts
{
  typeName?: string
}
```

### #/components/securitySchemes/Bearer

```ts
{
  "type": "http",
  "description": "JWT Authorization header using the Bearer scheme.",
  "scheme": "bearer",
  "bearerFormat": "JWT"
}
```