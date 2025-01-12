akahu - v1.15.2

# akahu - v1.15.2

## Table of contents

### API client config Type aliases

- [AkahuClientConfig](README.md#akahuclientconfig)
- [WebhookCacheConfig](README.md#webhookcacheconfig)

### Account Type aliases

- [Account](README.md#account)

### Auth Type aliases

- [AuthorizationToken](README.md#authorizationtoken)

### Category Type aliases

- [Category](README.md#category)

### Connection Type aliases

- [Connection](README.md#connection)

### Generic Type aliases

- [Paginated](README.md#paginated)
- [Cursor](README.md#cursor)

### Identity Type aliases

- [IdentityResult](README.md#identityresult)
- [IdentityVerifyNameQuery](README.md#identityverifynamequery)
- [AccountHolderNameVerificationSource](README.md#accountholdernameverificationsource)
- [PartyNameVerificationSource](README.md#partynameverificationsource)
- [IdentityVerifyNameResult](README.md#identityverifynameresult)

### Other Type aliases

- [PostRequestOptions](README.md#postrequestoptions)
- [Protocol](README.md#protocol)

### Parties Type aliases

- [PartyName](README.md#partyname)
- [PartyDob](README.md#partydob)
- [PartyPhoneNumber](README.md#partyphonenumber)
- [PartyEmail](README.md#partyemail)
- [PartyAddress](README.md#partyaddress)
- [PartyTaxNumber](README.md#partytaxnumber)
- [Party](README.md#party)

### Payment Type aliases

- [PaymentStatus](README.md#paymentstatus)
- [PaymentStatusCode](README.md#paymentstatuscode)
- [Payment](README.md#payment)
- [PaymentCreateParams](README.md#paymentcreateparams)
- [IrdPaymentCreateParams](README.md#irdpaymentcreateparams)
- [PaymentQueryParams](README.md#paymentqueryparams)

### Transaction Type aliases

- [TransactionType](README.md#transactiontype)
- [RawTransaction](README.md#rawtransaction)
- [PendingTransaction](README.md#pendingtransaction)
- [EnrichedTransaction](README.md#enrichedtransaction)
- [Transaction](README.md#transaction)
- [TransactionQueryParams](README.md#transactionqueryparams)

### Transfer Type aliases

- [TransferStatus](README.md#transferstatus)
- [Transfer](README.md#transfer)
- [TransferCreateParams](README.md#transfercreateparams)
- [TransferQueryParams](README.md#transferqueryparams)

### User Type aliases

- [User](README.md#user)

### Webhook Type aliases

- [WebhookType](README.md#webhooktype)
- [WebhookStatus](README.md#webhookstatus)
- [Webhook](README.md#webhook)
- [WebhookCreateParams](README.md#webhookcreateparams)
- [BasePayload](README.md#basepayload)
- [CancelledPayload](README.md#cancelledpayload)
- [TokenPayload](README.md#tokenpayload)
- [AccountPayload](README.md#accountpayload)
- [TransactionPayload](README.md#transactionpayload)
- [TransferPayload](README.md#transferpayload)
- [PaymentPayload](README.md#paymentpayload)
- [WebhookPayload](README.md#webhookpayload)
- [WebhookEvent](README.md#webhookevent)
- [WebhookEventQueryParams](README.md#webhookeventqueryparams)

### API client Classes

- [AkahuClient](classes/AkahuClient.md)

### Error Classes

- [AkahuErrorResponse](classes/AkahuErrorResponse.md)
- [AkahuWebhookValidationError](classes/AkahuWebhookValidationError.md)

### Resource Classes

- [AccountsResource](classes/AccountsResource.md)
- [AuthResource](classes/AuthResource.md)
- [CategoriesResource](classes/CategoriesResource.md)
- [ConnectionsResource](classes/ConnectionsResource.md)
- [IdentitiesResource](classes/IdentitiesResource.md)
- [PartiesResource](classes/PartiesResource.md)
- [PaymentsResource](classes/PaymentsResource.md)
- [TransactionsResource](classes/TransactionsResource.md)
- [TransfersResource](classes/TransfersResource.md)
- [UsersResource](classes/UsersResource.md)
- [WebhooksResource](classes/WebhooksResource.md)

### API client Interfaces

- [WebhookSigningKeyCache](interfaces/WebhookSigningKeyCache.md)

## API client config Type aliases

### AkahuClientConfig

Ƭ **AkahuClientConfig**: `Object`

Authentication and API endpoint configuration for [AkahuClient](classes/AkahuClient.md).

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `appToken` | `string` | appToken is required to access the Akahu API. |
| `appSecret?` | `string` | appSecret is only required for completing an OAuth code exchange, or to access app-specific endpoints.  For security reasons, this option must not be used client-side in the browser.  [https://developers.akahu.nz/reference/api_index](https://developers.akahu.nz/reference/api_index)   **`defaultvalue`** `undefined` |
| `apiVersion?` | `ApiVersion` | The Akahu API version. Currently the only supported value is "v1".  **`defaultvalue`** `v1` |
| `protocol?` | [`Protocol`](README.md#protocol) | The protocol used for Akahu API calls. The Akahu API only supports connections over HTTPS, so this option is only useful for test environments etc.  **`defaultvalue`** `https` |
| `host?` | `string` | The Akahu API hostname. It may be useful to override this in staging / testing environments.  **`defaultvalue`** `api.akahu.io` |
| `port?` | `number` | The Akahu API port. It may be useful to override this in staging / testing environments.  **`defaultvalue`** `undefined` |
| `headers?` | `Record`<`string`, `string`\> | Additional headers that will be included in each request. |
| `timeout?` | `number` | Timeout in ms for each request to the Akahu API.  If used in combination with `retries`, the timeout will be applied to each retried request. This means that the total time until an error is thrown due to a timeout will be `timeout * (retries + 1)` milliseconds.   **`defaultvalue`** `0` (no timeout) |
| `retries?` | `number` | The number of times that API requests will be retried in the case of network errors. Error responses from the Akahu API will not result in a retry.  **`defaultvalue`** `0` |
| `proxy?` | `Object` | Optional configuration for an HTTP proxy.  See the proxy section of the axios [request config](https://axios-http.com/docs/req_config) for more details. |
| `proxy.host` | `string` | - |
| `proxy.port` | `number` | - |
| `proxy.auth?` | `Object` | - |
| `proxy.auth.username` | `string` | - |
| `proxy.auth.password` | `string` | - |
| `proxy.protocol?` | `string` | - |
| `adapter?` | `AxiosAdapter` | Optional adapter function which will be passed through to the underlying Axios instance.  See [https://github.com/axios/axios/tree/v1.x/lib/adapters](https://github.com/axios/axios/tree/v1.x/lib/adapters). |

___

### WebhookCacheConfig

Ƭ **WebhookCacheConfig**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `cache` | [`WebhookSigningKeyCache`](interfaces/WebhookSigningKeyCache.md) |
| `key` | `string` |
| `maxAgeMs` | `number` |

___

## Account Type aliases

### Account

Ƭ **Account**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `_id` | `string` | A unique identifier for the account in the Akahu system. It is always be prefixed by `acc_` so that you can tell that it belongs to an account. |
| `_credentials` | `string` | When you connect accounts to Akahu you have to log in. Akahu keeps track of all of the accounts in that login session and gives them all a unique `_credentials` key, prefixed by `creds_`. |
| `connection` | [`Connection`](README.md#connection) | Information about the financial institution where the account is held (eg. ANZ bank). |
| `name` | `string` | The name of this account. If the connection allows customisation, the name will be the custom name (or nickname), eg. "Spending Account". Otherwise Akahu falls back to the product name, eg. "Super Saver". |
| `status` | ``"ACTIVE"`` \| ``"INACTIVE"`` | This tells you whether Akahu can currently sign in to the account to refresh it's data. It can be one of:  - `ACTIVE` → Akahu can sign in and refresh this account.  - `INACTIVE` → Akahu no longer has access to this account. This may be caused by the user revoking Akahu's access at the institution or changing their login credentials. When an account becomes `INACTIVE` your application should direct the the user back to the OAuth flow or to my.akahu.nz where they will be prompted to to re-establish this connection. |
| `type` | `AccountType` | Type of account, Akahu provides specific bank account types, and falls back to more general types for other types of connection. - `CHECKING` → An everyday spending account. - `SAVINGS` → A savings account. - `CREDITCARD` → A credit card. - `LOAN` → A loan account. - `KIWISAVER` → A KiwiSaver investment product. - `INVESTMENT` → A general investment product. - `TERMDEPOSIT` → A term deposit. - `FOREIGN` → An account holding a foreign currency. - `TAX` → An account with tax authorities. - `REWARDS` → An account for rewards points, e.g. Fly Buys or True Rewards. - `WALLET` → Available cash for investment or withdrawal from an investment provider. |
| `attributes` | `AccountAttribute`[] | The list of attributes indicates which abilities an account has. A list of: - `TRANSACTIONS` → account has transactions and supports retrieval of these via Akahu. - `TRANSFER_TO` → account can receive transfers from other accounts belonging to same set of credentials. - `TRANSFER_FROM` → account can initiate transfers to other accounts belonging to the same set of credentials. - `PAYMENT_TO` → account can receive payments from any Akahu account with the `PAYMENT_FROM` attribute. - `PAYMENT_FROM` → account can initiate payments to any Akahu account with the `PAYMENT_TO` attribute. |
| `formatted_account?` | `string` | If the account has a well defined account number (eg. a bank account number, or credit card number) this will be defined here with a standard format across connections. Credit cards will have at least 8 digits redacted. |
| `balance?` | `AccountBalance` | The account balance |
| `refreshed?` | `AccountRefreshState` | Akahu can refresh different parts of an account's data at different rates. The timestamps in the `refreshed` object tell you when that account data was last updated. This can be thought of as "Akahu's view of the account (balance/metadata/transactions) is up to date as of \$TIME". |
| `meta?` | `AccountMeta` | Metadata regarding this account |

___

## Auth Type aliases

### AuthorizationToken

Ƭ **AuthorizationToken**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `access_token` | `string` |
| `token_type` | ``"bearer"`` |
| `scope` | `string` |

___

## Category Type aliases

### Category

Ƭ **Category**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `_id` | `string` |
| `name` | `string` |
| `groups` | `Object` |

___

## Connection Type aliases

### Connection

Ƭ **Connection**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `_id` | `string` |
| `name` | `string` |
| `logo` | `string` |

___

## Generic Type aliases

### Paginated

Ƭ **Paginated**<`T`\>: `Object`

A "page" of results returned by paginated API endpoints.

Each page contains an array of zero-or-more returned objects nested under the
`items` key. In some cases - even if the returned `items` array is empty -
there may still be further pages available. Because if this it is important
to always check the value of `cursor.next` in the response.

The cursor pointing to the next page of results can be found nested under
`cursor.next`. If there are no further results available, `cursor.next` will
be `null`.

#### Type parameters

| Name |
| :------ |
| `T` |

#### Type declaration

| Name | Type |
| :------ | :------ |
| `items` | `T`[] |
| `cursor` | `Object` |
| `cursor.next` | `string` \| ``null`` |

___

### Cursor

Ƭ **Cursor**: `string` \| ``null`` \| `undefined`

Convenience type alias, useful when paging through multiple pages of results.

**`example`**
```typescript
import type { Cursor, Transaction } from "akahu";
const transactions: Transaction[] = [];
let cursor: Cursor;

do {
  const page = await akahu.transactions.list(userToken, { cursor });
  transactions.push(...page.items);
  cursor = page.cursor.next;
} while (cursor !== null);
```

___

## Identity Type aliases

### IdentityResult

Ƭ **IdentityResult**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `_id` | `string` |
| `status` | ``"PROCESSING"`` \| ``"COMPLETE"`` \| ``"ERROR"`` |
| `created_at` | `string` |
| `updated_at` | `string` |
| `expires_at` | `string` |
| `source` | `Record`<`string`, `any`\> |
| `errors?` | `string`[] |
| `identities?` | `Record`<`string`, `any`\>[] |
| `addresses?` | `Record`<`string`, `any`\>[] |
| `accounts?` | `Record`<`string`, `any`\>[] |

___

### IdentityVerifyNameQuery

Ƭ **IdentityVerifyNameQuery**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `family_name` | `string` | The user's family name which will be verified against the Akahu identity result. |
| `given_name?` | `string` | The user's given name which will be verified against the Akahu identity result. |
| `middle_name?` | `string` | The user's middle name which will be verified against the Akahu identity result. If the user has multiple middle names, provide them all separated by a space. |

___

### AccountHolderNameVerificationSource

Ƭ **AccountHolderNameVerificationSource**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | ``"HOLDER_NAME"`` | - |
| `match_result` | ``"MATCH"`` \| ``"PARTIAL_MATCH"`` | - |
| `meta` | `Object` | Metadata from the matched account |
| `meta.name` | `string` | The account name |
| `meta.holder` | `string` | The account holder name |
| `meta.account_number` | `string` | Formatted account number |
| `meta.bank` | `string` | The name of the bank |
| `meta.address?` | `string` | The address associated with the account |
| `meta.branch?` | `Object` | Branch details (if available) |
| `meta.branch._id` | `string` | - |
| `meta.branch.description` | `string` | - |
| `meta.branch.phone` | `string` | - |
| `meta.branch.address` | `Object` | - |
| `meta.branch.address.line1` | `string` | - |
| `meta.branch.address.city` | `string` | - |
| `meta.branch.address.country` | ``"New Zealand"`` | - |
| `meta.branch.address.postcode` | `string` | - |
| `meta.branch.address.line2?` | `string` | - |
| `meta.branch.address.line3?` | `string` | - |
| `verification` | `Object` | - |
| `verification.given_name` | `boolean` | - |
| `verification.given_initial` | `boolean` | - |
| `verification.middle_name` | `boolean` | - |
| `verification.middle_initial` | `boolean` | - |
| `verification.family_name` | `boolean` | - |

___

### PartyNameVerificationSource

Ƭ **PartyNameVerificationSource**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | ``"PARTY_NAME"`` | - |
| `match_result` | ``"MATCH"`` \| ``"PARTIAL_MATCH"`` | - |
| `meta` | `Object` | The matched party name data |
| `meta.type` | ``"INDIVIDUAL"`` \| ``"JOINT"`` \| ``"TRUST"`` \| ``"LLC"`` | - |
| `meta.family_name` | `string` | - |
| `meta.full_name` | `string` | - |
| `meta.initials?` | `string`[] | - |
| `meta.given_name?` | `string` | - |
| `meta.middle_name?` | `string` | - |
| `meta.prefix?` | `string` | - |
| `meta.gender?` | `string` | - |
| `verification` | `Object` | - |
| `verification.given_name` | `boolean` | - |
| `verification.given_initial` | `boolean` | - |
| `verification.middle_name` | `boolean` | - |
| `verification.middle_initial` | `boolean` | - |
| `verification.family_name` | `boolean` | - |

___

### IdentityVerifyNameResult

Ƭ **IdentityVerifyNameResult**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `sources` | ([`AccountHolderNameVerificationSource`](README.md#accountholdernameverificationsource) \| [`PartyNameVerificationSource`](README.md#partynameverificationsource))[] |

___

## Other Type aliases

### PostRequestOptions

Ƭ **PostRequestOptions**: `Object`

Additional options for a POST request

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `idempotencyKey?` | `string` | Specifying this key allows you to safely retry POST requests without the risk of taking the same action twice. This is useful when an API call is disrupted in transit and you do not receive a response or you wish to protect against your application issuing duplicate requests.  **`default`** auto generated uuid |

___

### Protocol

Ƭ **Protocol**: ``"http"`` \| ``"https"``

___

## Parties Type aliases

### PartyName

Ƭ **PartyName**: `Object`

The user's name as sourced from the connected institution.

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `value` | `string` | The name value in the format provided by the connected institution. e.g. John Smith, Mr John Smith, MR JOHN SMITH |

___

### PartyDob

Ƭ **PartyDob**: `Object`

The user's date of birth as sourced from the connected institution.

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `value` | `string` | The user's date of birth in the format YYYY-MM-DD. |

___

### PartyPhoneNumber

Ƭ **PartyPhoneNumber**: `Object`

The user's phone number as sourced from the connected institution.

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `subtype` | ``"MOBILE"`` \| ``"HOME"`` \| ``"WORK"`` | - |
| `verified` | `boolean` | - |
| `value` | `string` | The value of the phone number. |

___

### PartyEmail

Ƭ **PartyEmail**: `Object`

The user's email address as sourced from the connected institution.

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `subtype` | ``"PRIMARY"`` | - |
| `verified` | `boolean` | - |
| `value` | `string` | The value of the email address. |

___

### PartyAddress

Ƭ **PartyAddress**: `Object`

The user's address as sourced from the connected institution.

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `subtype` | ``"RESIDENTIAL"`` \| ``"POSTAL"`` | - |
| `value` | `string` | The raw address value from the connected institution. |
| `formatted` | `string` | A consistently formatted/normalised version of the address. |
| `components` | `Object` | Individual components of the normalised address. |
| `components.street` | `string` | - |
| `components.suburb` | `string` | - |
| `components.city` | `string` | - |
| `components.region` | `string` | - |
| `components.postal_code` | `string` | - |
| `components.country` | `string` | - |
| `google_maps_place_id` | `string` | Google Maps API Place ID for this address.  [https://developers.google.com/maps/documentation/places/web-service/place-id](https://developers.google.com/maps/documentation/places/web-service/place-id) |

___

### PartyTaxNumber

Ƭ **PartyTaxNumber**: `Object`

The user's tax (IRD) number as sourced from the connected institution.

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `value` | `string` | The IRD number in the format XXX-XXX-XXX |

___

### Party

Ƭ **Party**: `Object`

Identity data relating to the party that the user has logged-in to their
institution as when connecting accounts to Akahu. i.e. the user's "profile"
information at the connected institution.

All keys are optional depending on the scopes granted to your app.

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `_id` | `string` | - |
| `_connection` | `string` | The connection id identifying the institution that the data was sourced from |
| `_user` | `string` | - |
| `type` | ``"INDIVIDUAL"`` \| ``"JOINT"`` \| ``"TRUST"`` \| ``"LLC"`` | - |
| `name?` | [`PartyName`](README.md#partyname) | - |
| `dob?` | [`PartyDob`](README.md#partydob) | - |
| `tax_number?` | [`PartyTaxNumber`](README.md#partytaxnumber) | - |
| `phone_numbers?` | [`PartyPhoneNumber`](README.md#partyphonenumber)[] | - |
| `email_addresses?` | [`PartyEmail`](README.md#partyemail)[] | - |
| `addresses?` | [`PartyAddress`](README.md#partyaddress)[] | - |

___

## Payment Type aliases

### PaymentStatus

Ƭ **PaymentStatus**: ``"READY"`` \| ``"PENDING_APPROVAL"`` \| ``"PAUSED"`` \| ``"SENT"`` \| ``"DECLINED"`` \| ``"ERROR"`` \| ``"CANCELLED"``

___

### PaymentStatusCode

Ƭ **PaymentStatusCode**: ``"INTERNAL_ERROR"`` \| ``"BANK_ERROR"`` \| ``"UNAVAILABLE"`` \| ``"INVALID_ACCOUNT"`` \| ``"INSUFFICIENT_FUNDS"`` \| ``"SINGLE_LIMIT_EXCEEDED"`` \| ``"DAILY_LIMIT_EXCEEDED"`` \| ``"AKAHU_LIMIT_EXCEEDED"`` \| ``"MFA_UNSUPPORTED"`` \| ``"MULTISIG_UNSUPPORTED"`` \| ``"AUTHENTICATION_FAILED"`` \| ``"MFA_FAILED"`` \| ``"AFTER_HOURS"`` \| ``"USER_CANCELLED"`` \| ``"APP_CANCELLED"`` \| ``"AKAHU_CANCELLED"``

___

### Payment

Ƭ **Payment**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `_id` | `string` |
| `from` | `string` |
| `to` | `Object` |
| `to.name` | `string` |
| `to.account_number` | `string` |
| `amount` | `number` |
| `meta` | `Object` |
| `meta.source` | `Object` |
| `meta.source.code?` | `string` |
| `meta.source.reference?` | `string` |
| `meta.destination` | `Object` |
| `meta.destination.particulars?` | `string` |
| `meta.destination.code?` | `string` |
| `meta.destination.reference?` | `string` |
| `sid` | `string` |
| `status` | [`PaymentStatus`](README.md#paymentstatus) |
| `final` | `boolean` |
| `timeline` | { `status`: [`PaymentStatus`](README.md#paymentstatus) ; `time`: `string` ; `eta?`: `string`  }[] |
| `created_at` | `string` |
| `updated_at` | `string` |
| `status_code?` | [`PaymentStatusCode`](README.md#paymentstatuscode) |
| `status_text?` | `string` |
| `approval_type?` | ``"BANK"`` \| ``"USER"`` |
| `received_at?` | `string` |
| `timeout_at?` | `string` |

___

### PaymentCreateParams

Ƭ **PaymentCreateParams**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `from` | `string` | The Akahu account id from which the payment will be made. The `from` account id **must** refer to an account that has been linked by the user for which this request is authenticated.  An account id starts with `acc_...`. |
| `amount` | `number` | The dollar amount for the payment. This must be a numeric value with no more than 2 decimal places. |
| `to` | `Object` | The details of the payee bank account to which the payment will be made. |
| `to.name` | `string` | The payee account holder name |
| `to.account_number` | `string` | The full payee account number. |
| `meta?` | `Object` | Optional metadata to send with the payment. |
| `meta.source?` | `Object` | Metadata which will appear on the payers account statement.  **`remarks`** **Note:** `particulars` is not an accepted field. Akahu reserves this field on the source/payer statement for support and transaction verification. |
| `meta.source.code?` | `string` | - |
| `meta.source.reference?` | `string` | - |
| `meta.destination?` | `Object` | Metadata which will appear on the payees account statement |
| `meta.destination.particulars?` | `string` | - |
| `meta.destination.code?` | `string` | - |
| `meta.destination.reference?` | `string` | - |

___

### IrdPaymentCreateParams

Ƭ **IrdPaymentCreateParams**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `from` | `string` | The Akahu account id from which the payment will be made. The `from` account id **must** refer to an account that has been linked by the user for which this request is authenticated.  An account id starts with `acc_...`. |
| `amount` | `number` | The dollar amount for the payment. This must be a numeric value with no more than 2 decimal places. |
| `meta` | `Object` | Required tax payment metadata to send with the payment. |
| `meta.tax_number` | `string` | The IRD/GST number associated with the payment. |
| `meta.tax_type` | `string` | The 3 character IRD tax type code that tells IRD what type of tax the payment is for. [https://www.ird.govt.nz/managing-my-tax/make-a-payment/choosing-the-right-account-type](https://www.ird.govt.nz/managing-my-tax/make-a-payment/choosing-the-right-account-type) |
| `meta.tax_period?` | `string` | The end date of the tax period which this payment is for, formatted as an ISO 8601 date e.g. 1970-01-01.  This is required by IRD for _most_ tax payments, however there are certain payment types that do not require it (e.g. ARR, KSS, LGL). For the complete list of exclusions see: [https://www.ird.govt.nz/managing-my-tax/make-a-payment/ways-of-paying/paying-electronically](https://www.ird.govt.nz/managing-my-tax/make-a-payment/ways-of-paying/paying-electronically) |

___

### PaymentQueryParams

Ƭ **PaymentQueryParams**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `start?` | `string` | The start date of the query as an ISO 8601 string.  **`defaultvalue`** `30 days ago` |
| `end?` | `string` | The end date of the query as an ISO 8601 string.  **`defaultvalue`** `today` |

___

## Transaction Type aliases

### TransactionType

Ƭ **TransactionType**: ``"CREDIT"`` \| ``"DEBIT"`` \| ``"PAYMENT"`` \| ``"TRANSFER"`` \| ``"STANDING ORDER"`` \| ``"EFTPOS"`` \| ``"INTEREST"`` \| ``"FEE"`` \| ``"CREDIT CARD"`` \| ``"TAX"`` \| ``"DIRECT DEBIT"`` \| ``"DIRECT CREDIT"`` \| ``"ATM"`` \| ``"LOAN"``

___

### RawTransaction

Ƭ **RawTransaction**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `_id` | `string` | The unique id for the transaction |
| `_user` | `string` | The unique id of the user that the transaction is associated with. |
| `_account` | `string` | The unique id of the account that the transaction is associated with. |
| `_connection` | `string` | The unique id of the connection that the transaction is associated with. |
| `created_at` | `string` | The time at which the transaction was retrieved by Akahu. Formatted as an ISO 8601 timestamp. |
| `updated_at` | `string` | The time at which the transaction was last updated by Akahu. Formatted as an ISO 8601 timestamp. |
| `date` | `string` | The date that the transaction was posted as reported by the bank integration. Formatted as an ISO 8601 timestamp. |
| `hash` | `string` | An identification string based on the contents of the transaction and the account from which the transaction was fetched.  **`deprecated`** Prefer {@link RawTransaction._id `_id`} to uniquely identify transactions. |
| `description` | `string` | The transaction description as reported by the bank integration. |
| `amount` | `number` | The monetary value of the transaction. |
| `type` | [`TransactionType`](README.md#transactiontype) | The type of the transaction. |
| `balance?` | `number` | The account balance after receipt of this transaction (when available). |

___

### PendingTransaction

Ƭ **PendingTransaction**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `_user` | `string` | The unique id of the user that the pending transaction is associated with. |
| `_account` | `string` | The unique id of the account that the pending transaction is associated with. |
| `_connection` | `string` | The unique id of the account that the pending transaction is associated with. |
| `updated_at` | `string` | The time at which the transaction was updated by Akahu. Formatted as an ISO 8601 timestamp. |
| `date` | `string` | The date that the transaction was posted as reported by the bank integration. Formatted as an ISO 8601 timestamp. |
| `description` | `string` | - |
| `amount` | `number` | - |
| `type` | [`TransactionType`](README.md#transactiontype) | - |

___

### EnrichedTransaction

Ƭ **EnrichedTransaction**: [`RawTransaction`](README.md#rawtransaction) & { `merchant`: { `_id`: `string` ; `name`: `string` ; `website?`: `string`  } ; `category`: { `_id`: `string` ; `name`: `string` ; `groups`: { [groupKey: string]: { `_id`: `string` ; `name`: `string`  };  }  } ; `meta`: { `particulars?`: `string` ; `code?`: `string` ; `reference?`: `string` ; `other_account?`: `string` ; `conversion?`: `string` ; `logo?`: `string`  }  }

___

### Transaction

Ƭ **Transaction**: [`RawTransaction`](README.md#rawtransaction) \| [`EnrichedTransaction`](README.md#enrichedtransaction)

___

### TransactionQueryParams

Ƭ **TransactionQueryParams**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `start?` | `string` | The start date of the query as an ISO 8601 string.  **`defaultvalue`** `30 days ago` |
| `end?` | `string` | The end date of the query as an ISO 8601 string.  **`defaultvalue`** `today` |
| `cursor?` | [`Cursor`](README.md#cursor) | The pagination cursor received as part of a previous paginated response.  If this query parameter is omitted, only the first page of transaction results will be retrieved. The cursor to fetch the next page of results can be retrieved from a given `page` of response data, nested under `page.cursor.next`. If this value is `undefined`, it means that the last page has been reached. |

___

## Transfer Type aliases

### TransferStatus

Ƭ **TransferStatus**: ``"READY"`` \| ``"PENDING_APPROVAL"`` \| ``"SENT"`` \| ``"DECLINED"`` \| ``"ERROR"`` \| ``"PAUSED"`` \| ``"CANCELLED"``

___

### Transfer

Ƭ **Transfer**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `_id` | `string` |
| `from` | `string` |
| `to` | `string` |
| `amount` | `number` |
| `sid` | `string` |
| `status` | [`TransferStatus`](README.md#transferstatus) |
| `final` | `boolean` |
| `timeline` | { `status`: [`TransferStatus`](README.md#transferstatus) ; `time`: `string`  }[] |
| `created_at` | `string` |
| `updated_at` | `string` |
| `status_text?` | `string` |

___

### TransferCreateParams

Ƭ **TransferCreateParams**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `from` | `string` | The Akahu account id from which the transfer will be made. The `from` account id **must** refer to an account that has been linked by the user for which this request is authenticated.  An account id starts with `acc_...`. |
| `to` | `string` | The Akahu account id to which the transfer will be made. The `to` account id **must** refer to an account that has been linked by the user for which this request is authenticated.  An account id starts with `acc_...`. |
| `amount` | `number` | The dollar amount for the transfer. This must be a numeric value with no more than 2 decimal places. |

___

### TransferQueryParams

Ƭ **TransferQueryParams**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `start?` | `string` | The start date of the query as an ISO 8601 string.  **`defaultvalue`** `30 days ago` |
| `end?` | `string` | The end date of the query as an ISO 8601 string.  **`defaultvalue`** `today` |

___

## User Type aliases

### User

Ƭ **User**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `_id` | `string` | Akahu's unique identifier for this user. |
| `access_granted_at` | `string` | The timestamp that the user first granted your app access to their accounts (i.e. the time at which your user token was issued). Formatted as an ISO 8601 timestamp. |
| `email?` | `string` | The email address that this user used to register with Akahu.  This will always be present if your app has the `AKAHU` scope. |
| `preferred_name?` | `string` | The user's preferred name, if they have provided it by updating their profile at https://my.akahu.nz. This will not be available for most users. |
| `first_name?` | `string` | The user's first name, if they have provided it.  **`deprecated`** Only present on some legacy users. You probably want [party](https://developers.akahu.nz/reference/get_parties) data instead, which is sourced from the user's connected financial institution(s). |
| `last_name?` | `string` | The user's last name, if they have provided it.  **`deprecated`** Only present on some legacy users. You probably want [party](https://developers.akahu.nz/reference/get_parties) data instead, which is sourced from the user's connected financial institution(s). |
| `mobile?` | `undefined` | **`deprecated`** This field is unused. You probably want [party](https://developers.akahu.nz/reference/get_parties) data instead, which is sourced from the user's connected financial institution(s). |

___

## Webhook Type aliases

### WebhookType

Ƭ **WebhookType**: ``"TOKEN"`` \| ``"ACCOUNT"`` \| ``"TRANSACTION"`` \| ``"TRANSFER"`` \| ``"PAYMENT"``

___

### WebhookStatus

Ƭ **WebhookStatus**: ``"SENT"`` \| ``"FAILED"`` \| ``"RETRY"``

___

### Webhook

Ƭ **Webhook**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `_id` | `string` |
| `type` | [`WebhookType`](README.md#webhooktype) |
| `state` | `string` |
| `url` | `string` |
| `created_at` | `string` |
| `updated_at` | `string` |
| `last_called_at` | `string` |

___

### WebhookCreateParams

Ƭ **WebhookCreateParams**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `webhook_type` | [`WebhookType`](README.md#webhooktype) | - |
| `state?` | `string` | The `state` value will be This value should allow you to uniquely iden |

___

### BasePayload

Ƭ **BasePayload**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `webhook_type` | [`WebhookType`](README.md#webhooktype) |
| `webhook_code` | `string` |
| `state` | `string` |

___

### CancelledPayload

Ƭ **CancelledPayload**: [`BasePayload`](README.md#basepayload) & { `webhook_code`: ``"WEBHOOK_CANCELLED"``  }

___

### TokenPayload

Ƭ **TokenPayload**: [`BasePayload`](README.md#basepayload) & { `webhook_type`: ``"TOKEN"`` ; `webhook_code`: ``"DELETE"`` ; `item_id`: `string`  }

___

### AccountPayload

Ƭ **AccountPayload**: [`BasePayload`](README.md#basepayload) & { `webhook_type`: ``"ACCOUNT"``  } & { `webhook_code`: ``"CREATE"`` \| ``"DELETE"`` ; `item_id`: `string`  } \| { `webhook_code`: ``"UPDATE"`` ; `item_id`: `string` ; `updated_fields`: `string`[]  }

___

### TransactionPayload

Ƭ **TransactionPayload**: [`BasePayload`](README.md#basepayload) & { `webhook_type`: ``"TRANSACTION"``  } & { `webhook_code`: ``"INITIAL_UPDATE"`` \| ``"DEFAULT_UPDATE"`` ; `item_id`: `string` ; `new_transactions`: `number` ; `new_transaction_ids`: `string`[]  } \| { `webhook_code`: ``"DELETE"`` ; `item_id`: `string` ; `removed_transactions`: `string`[]  }

___

### TransferPayload

Ƭ **TransferPayload**: [`BasePayload`](README.md#basepayload) & { `webhook_type`: ``"TRANSFER"``  } & { `webhook_code`: ``"UPDATE"`` ; `item_id`: `string` ; `status`: [`TransferStatus`](README.md#transferstatus) ; `status_text?`: `string`  } \| { `webhook_code`: ``"RECEIVED"`` ; `item_id`: `string` ; `received_at`: `string`  }

___

### PaymentPayload

Ƭ **PaymentPayload**: [`BasePayload`](README.md#basepayload) & { `webhook_type`: ``"PAYMENT"``  } & { `webhook_code`: ``"UPDATE"`` ; `item_id`: `string` ; `status`: [`TransferStatus`](README.md#transferstatus) ; `status_text?`: `string` ; `status_code?`: `string`  } \| { `webhook_code`: ``"RECEIVED"`` ; `item_id`: `string` ; `received_at`: `string`  }

___

### WebhookPayload

Ƭ **WebhookPayload**: [`CancelledPayload`](README.md#cancelledpayload) \| [`TokenPayload`](README.md#tokenpayload) \| [`AccountPayload`](README.md#accountpayload) \| [`TransactionPayload`](README.md#transactionpayload) \| [`TransferPayload`](README.md#transferpayload) \| [`PaymentPayload`](README.md#paymentpayload)

___

### WebhookEvent

Ƭ **WebhookEvent**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `_id` | `string` | The unique identifier for this webhook event. |
| `_hook` | `string` | The unique identifier for this webhook subscription. This can be used with the `unsubscribe` method to remove this webhook subscription if it is no longer required. |
| `status` | [`WebhookStatus`](README.md#webhookstatus) | The delivery status of this webhook event. |
| `payload` | [`WebhookPayload`](README.md#webhookpayload) | The main payload of the webhook event. |
| `created_at` | `string` | The timestamp at which this webhook event was created. |
| `updated_at` | `string` | The timestamp at which this webhook event was last updated. |
| `last_failed_at?` | `string` | If the webhook event has at any point failed to send, the timestamp at which the last attempt was made. |

___

### WebhookEventQueryParams

Ƭ **WebhookEventQueryParams**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `status` | [`WebhookStatus`](README.md#webhookstatus) | **Required:** The webhook delivery status. |
| `start?` | `string` | The start date of the query as an ISO 8601 string.  **`defaultvalue`** `30 days ago` |
| `end?` | `string` | The end date of the query as an ISO 8601 string.  **`defaultvalue`** `today` |
