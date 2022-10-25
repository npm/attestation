# npm publish attestation (v0.1)

The npm publish attestation conforms to the [in-toto attestation spec (v0.1.0)]([url](https://github.com/in-toto/attestation/tree/v0.1.0/spec)).

### Statement

```json
{
  "_type": "https://in-toto.io/Statement/v0.1",
  "subject": [{
    "name": "pkg:npm/@scope/package-foo@1.4.3",
    "digest": { "sha512": "41o0P/CEffYGDqvo2pHQXRBOfFOxvYY3WkwkQTy..." }
  }],
  "predicateType": "https://github.com/npm/attestation/tree/main/specs/publish/v0.1",
  "predicate": {
    "name": "@scope/package-foo",
    "version": "1.4.3",
    "registry": "https://registry.npmjs.org",
  }
}
```

- `subject[0].name`: A [package url (purl)]([url](https://github.com/package-url/purl-spec))
- `subject[0].digest`: Sha-512 hexdigest of the published tarball.
- `predicate.name`: Package name
- `predicate.version`: Published version
- `predicate.registry`: Registry URL
