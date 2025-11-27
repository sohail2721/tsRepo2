
# Client Class Documentation

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | `Environment` | The API environment. <br> **Default: `Environment.Production`** |
| timeout | `number` | Timeout for API calls.<br>*Default*: `0` |
| httpClientOptions | [`Partial<HttpClientOptions>`](../doc/http-client-options.md) | Stable configurable http client options. |
| unstableHttpClientOptions | `any` | Unstable configurable http client options. |
| petstoreAuthCredentials | [`PetstoreAuthCredentials`](auth/oauth-2-implicit-grant.md) | The credential object for petstoreAuth |
| apiKeyCredentials | [`ApiKeyCredentials`](auth/custom-header-signature.md) | The credential object for apiKey |

The API client can be initialized as follows:

```ts
import {
  Client,
  Environment,
  OAuthScopePetstoreAuthEnum,
} from 'petstore-pkg';

const client = new Client({
  petstoreAuthCredentials: {
    oAuthClientId: 'OAuthClientId',
    oAuthRedirectUri: 'OAuthRedirectUri',
    oAuthScopes: [
      OAuthScopePetstoreAuthEnum.Writepets,
      OAuthScopePetstoreAuthEnum.Readpets
    ]
  },
  apiKeyCredentials: {
    'api_key': 'api_key'
  },
  timeout: 0,
  environment: Environment.Production,
});
```

