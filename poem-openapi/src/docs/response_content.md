Define a OpenAPI response content.

# Item parameters

| Attribute    | description               | Type   | Optional |
|--------------|---------------------------|--------|----------|
| content_type | Specify the content type. | string | Y        |

# Examples

```rust
use poem_openapi::{
    payload::{Binary, Json, PlainText},
    ApiResponse, ResponseContent,
};

#[derive(ResponseContent)]
enum MyResponseContent {
    A(Json<i32>),
    B(PlainText<String>),
    C(Binary<Vec<u8>>),
}

#[derive(ApiResponse)]
enum MyResponse {
    #[oai(status = 200)]
    Ok(MyResponseContent),
}
```
