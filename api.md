# JackAI Platform OS Hub API (public subset) Kotlin API

<!-- omniwrap-api-reference eyJjb250cmFjdF9maW5nZXJwcmludCI6ImM3Y2E1ZTVlYmI0YzA5MjkxMGVjNzJiMzcxZTE4ODMwMzM1OGM1ZTM0ZDI5MDhjMGE4OGY3ODJhMjQxMTYyY2YiLCJvcGVyYXRpb25fY291bnQiOjgsInJlbmRlcmVyIjoia290bGluIiwidmVyc2lvbiI6IjEuNS4wIn0 -->

This generated index is tied to Semantic IR `1.14.0` and contract fingerprint `c7ca5e5ebb4c092910ec72b371e188303358c5e34d2908c0a88f782a241162cf`. Every operation below is rendered from the same semantic contract and artifact-attested public member allocation as the SDK.

SDK maturity: **experimental**  
Artifact evidence: [`omniwrap-artifact.json`](omniwrap-artifact.json) binds this file by SHA-256 and is revalidated by the package gate.

## Client hooks and tracing

`ClientOptions(hooks = RequestHooks(...))` registers four callbacks. Every attempt starts with `beforeRequest` and ends with exactly one of `onRetry` (another attempt follows), `afterResponse` (the success the call returns) or `onError` (the failure the call reports). Each receives the operation id, the HTTP method, the URL, the request headers, the attempt number (from 1), the time elapsed since the call started and, once the server answered, the HTTP status. No context carries a credential: `Authorization`, `Proxy-Authorization`, `Cookie`, every API-key header and API-key query parameter, and any configured credential value read `[redacted]`. Every context is an immutable `HookContext`: no hook can change the request.

`ClientOptions(tracer = ...)` opens one span per call through the tracer interface this SDK defines, named after the operation id, with `http.request.method`, `http.response.status_code` and `http.request.resend_count`. It needs no tracing library; README.md maps it onto the OpenTelemetry API.

## Resource `health`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJoZWFsdGguZ2V0SGVhbHRoIiwibWV0aG9kIjoiR0VUIiwib3BlcmF0aW9uX2lkIjoiZ2V0SGVhbHRoIiwicGF0aCI6Ii9oZWFsdGgiLCJyZXNvdXJjZSI6ImhlYWx0aCIsInNlY3Rpb25fc2hhMjU2IjoiNjM0NWYyOTQxZDUyYzU2M2NiODA5MDZkYmFmOTA5NmE3ZWE2YTA0ODAxMmJjODlmMTQ2NDgxNGQ2YTg4NjQ4YyIsInNpZ25hdHVyZV9zaGEyNTYiOiI2NGNhZmRlNGUzMWFmNWIxMDMxYjZmYjk5ZWFlMWRkMGJmZWJkMzhiMGExYWRjMmIyYzJjY2JhNWU3ZWZiNDcyIn0 -->
### `client.health.getHealth`

Operation ID: `getHealth`  
Route: `GET` `/health`  
Equivalent member: `client.getHealth`  

#### Signature

```kotlin
suspend fun getHealth(params: GetHealthParams, requestOptions: RequestOptions = RequestOptions()): ApiResult<Unit>
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Hub liveness status | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```kotlin
val result = client.health.getHealth()
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRIZWFsdGgifQ -->

## Resource `kernel`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJrZXJuZWwuZmFpbFVzYWdlUXVvdGEiLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoiZmFpbFVzYWdlUXVvdGEiLCJwYXRoIjoiL3YxL2tlcm5lbC91c2FnZS9mYWlsIiwicmVzb3VyY2UiOiJrZXJuZWwiLCJzZWN0aW9uX3NoYTI1NiI6IjY2MGE0MDdmZjQ5NTc2OWZjNTNlNTYzMDQ4YmQxMDA0MDZmMTkyMGMzZTQ0ZjIyY2Q4NjFlNjM2MmY3NjZkZjYiLCJzaWduYXR1cmVfc2hhMjU2IjoiZjMzMWY3ZmY5MjM3OGUzY2QxMTNiNjczYTMxZTFhZWIzNTQxY2NhM2I4ZmMzNzU4NTNjYzU0ZDA3MzI4MmMxZiJ9 -->
### `client.kernel.failUsageQuota`

Operation ID: `failUsageQuota`  
Route: `POST` `/v1/kernel/usage/fail`  
Equivalent member: `client.failUsageQuota`  

#### Signature

```kotlin
suspend fun failUsageQuota(params: FailUsageQuotaParams, requestOptions: RequestOptions = RequestOptions()): ApiResult<Unit>
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Reservation released | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```kotlin
val result = client.kernel.failUsageQuota()
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJmYWlsVXNhZ2VRdW90YSJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJrZXJuZWwuZmluYWxpemVVc2FnZVF1b3RhIiwibWV0aG9kIjoiUE9TVCIsIm9wZXJhdGlvbl9pZCI6ImZpbmFsaXplVXNhZ2VRdW90YSIsInBhdGgiOiIvdjEva2VybmVsL3VzYWdlL2ZpbmFsaXplIiwicmVzb3VyY2UiOiJrZXJuZWwiLCJzZWN0aW9uX3NoYTI1NiI6IjIwOTI5MWQ1NjU3YzYwN2Y3NDVlZDFkZWNhMDY4NmUzZDBmMWNjZjdlNTQzYzY1NTgxNmNlMjljMjUwMDljZjAiLCJzaWduYXR1cmVfc2hhMjU2IjoiMThkZmY3MWJhMTlhMDdjOGVjNWE3MDg2ZDc3NmMwNGEyYmEyMTU2YTdkYWMyZmFhZjJlYjQ4M2Y0ZjBlYjU3YyJ9 -->
### `client.kernel.finalizeUsageQuota`

Operation ID: `finalizeUsageQuota`  
Route: `POST` `/v1/kernel/usage/finalize`  
Equivalent member: `client.finalizeUsageQuota`  

#### Signature

```kotlin
suspend fun finalizeUsageQuota(params: FinalizeUsageQuotaParams, requestOptions: RequestOptions = RequestOptions()): ApiResult<Unit>
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Reservation finalized | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```kotlin
val result = client.kernel.finalizeUsageQuota()
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJmaW5hbGl6ZVVzYWdlUXVvdGEifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJrZXJuZWwucmVzZXJ2ZVVzYWdlUXVvdGEiLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoicmVzZXJ2ZVVzYWdlUXVvdGEiLCJwYXRoIjoiL3YxL2tlcm5lbC91c2FnZS9yZXNlcnZlIiwicmVzb3VyY2UiOiJrZXJuZWwiLCJzZWN0aW9uX3NoYTI1NiI6ImMwYjI3ZGQ3ZDVlODZjMDk5YzhjYzljNGUwOWZmMmFhMDc3YTk1YjhhYjJmZjk0NDczZDliZDdjYmQyNDFjZjkiLCJzaWduYXR1cmVfc2hhMjU2IjoiNGIxNjY3MjljMjY3NzE4NWE0YWM3NzJiM2Q2Zjg3NDdkZmZmZTk2OTJlOGE2YTRlYzgzMWQ5MDUwODFkN2NlNiJ9 -->
### `client.kernel.reserveUsageQuota`

Operation ID: `reserveUsageQuota`  
Route: `POST` `/v1/kernel/usage/reserve`  
Equivalent member: `client.reserveUsageQuota`  

#### Signature

```kotlin
suspend fun reserveUsageQuota(params: ReserveUsageQuotaParams, requestOptions: RequestOptions = RequestOptions()): ApiResult<Unit>
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Reservation lease created | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```kotlin
val result = client.kernel.reserveUsageQuota()
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJyZXNlcnZlVXNhZ2VRdW90YSJ9 -->

## Resource `user`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJ1c2VyLmdldEN1cnJlbnRVc2VyIiwibWV0aG9kIjoiR0VUIiwib3BlcmF0aW9uX2lkIjoiZ2V0Q3VycmVudFVzZXIiLCJwYXRoIjoiL3VzZXIvbWUiLCJyZXNvdXJjZSI6InVzZXIiLCJzZWN0aW9uX3NoYTI1NiI6IjNlMGM0MGViYmExZmFmNzUwNzg2NTdiYzM4NDc0YmZjNTJhOGNlYWJhYTdiYmYxNDMzMThkNWI4ZjcwY2FmYzkiLCJzaWduYXR1cmVfc2hhMjU2IjoiZTY0MzZjNTNmYmM0ZDBkNzM2ODU0YjFjMDFmN2I3Njk1MjY0ZWNkZmVhOWZmNWJhZDhjZDdkN2UxZDU1MDIyNSJ9 -->
### `client.user.getCurrentUser`

Operation ID: `getCurrentUser`  
Route: `GET` `/user/me`  
Equivalent member: `client.getCurrentUser`  

#### Signature

```kotlin
suspend fun getCurrentUser(params: GetCurrentUserParams, requestOptions: RequestOptions = RequestOptions()): ApiResult<Unit>
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Current user context | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```kotlin
val result = client.user.getCurrentUser()
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRDdXJyZW50VXNlciJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJ1c2VyLmdldFNpZ251cFBvbGljeSIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6ImdldFNpZ251cFBvbGljeSIsInBhdGgiOiIvdXNlci9hdXRoL3NpZ251cC1wb2xpY3kiLCJyZXNvdXJjZSI6InVzZXIiLCJzZWN0aW9uX3NoYTI1NiI6ImUyODVhMTIwMDZkOWJiNjBmNmZhMzBjZTI0OWUwYzA1YTgxYWI5MzZhNGZjM2U5Njk2NWVmZmZjMzFiY2UxYWQiLCJzaWduYXR1cmVfc2hhMjU2IjoiMDdmYzZiZWY4M2NhOGJiMzc4ZjIzNmUzOTIyZTkxY2RhNjg5YmViMTUyYWIyNDcyODViZWZlODJkNTE4MTNlNiJ9 -->
### `client.user.getSignupPolicy`

Operation ID: `getSignupPolicy`  
Route: `GET` `/user/auth/signup-policy`  
Equivalent member: `client.getSignupPolicy`  

#### Signature

```kotlin
suspend fun getSignupPolicy(params: GetSignupPolicyParams, requestOptions: RequestOptions = RequestOptions()): ApiResult<Unit>
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Current signup policy | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```kotlin
val result = client.user.getSignupPolicy()
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRTaWdudXBQb2xpY3kifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJ1c2VyLmxvZ2luVXNlciIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJsb2dpblVzZXIiLCJwYXRoIjoiL3VzZXIvYXV0aC9sb2dpbiIsInJlc291cmNlIjoidXNlciIsInNlY3Rpb25fc2hhMjU2IjoiOTMyNDU3NmMyNjdlYWYwY2VlNThlODc2NjUzNDA4NmQzOWRkNGI2ZWUwMWJiMzhhZTI2MGYyNGEwOGY5YWRjYiIsInNpZ25hdHVyZV9zaGEyNTYiOiIxZDRkMTljNDY4NGVkNmJkYzU0ZDA5MGM0MmU5MzM3NDU2Y2Q3MGZkMWY3MDUwYjRmYTk4NGM2ZTQwYTAyZDA2In0 -->
### `client.user.loginUser`

Operation ID: `loginUser`  
Route: `POST` `/user/auth/login`  
Equivalent member: `client.loginUser`  

#### Signature

```kotlin
suspend fun loginUser(params: LoginUserParams, requestOptions: RequestOptions = RequestOptions()): ApiResult<Unit>
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Authenticated session or MFA challenge | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```kotlin
val result = client.user.loginUser()
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsb2dpblVzZXIifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJ1c2VyLnN1Ym1pdFdhaXRsaXN0UmVxdWVzdCIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJzdWJtaXRXYWl0bGlzdFJlcXVlc3QiLCJwYXRoIjoiL3VzZXIvYXV0aC93YWl0bGlzdCIsInJlc291cmNlIjoidXNlciIsInNlY3Rpb25fc2hhMjU2IjoiZWNiMTFlYWQwMzRlOGQ3YTAzMWUxYzM0OTg4ZmZlYmMxNjc2MjFlMjI1NTBkZTI0OTZmZmI4ZWQxNTQ1NjViMSIsInNpZ25hdHVyZV9zaGEyNTYiOiJhODE3NzRhZWUzM2RlODg3NDA2ZWFiMjhlOTc4ODNmNmJkNjgwNjY2MTBlNjAxY2U0MTE0ZTI4NWJhNTIzMDhjIn0 -->
### `client.user.submitWaitlistRequest`

Operation ID: `submitWaitlistRequest`  
Route: `POST` `/user/auth/waitlist`  
Equivalent member: `client.submitWaitlistRequest`  

#### Signature

```kotlin
suspend fun submitWaitlistRequest(params: SubmitWaitlistRequestParams, requestOptions: RequestOptions = RequestOptions()): ApiResult<Unit>
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `202` | Waitlist request recorded with an opaque WL- reference | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```kotlin
val result = client.user.submitWaitlistRequest()
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJzdWJtaXRXYWl0bGlzdFJlcXVlc3QifQ -->

