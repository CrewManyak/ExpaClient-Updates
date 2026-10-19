# EXPA Client — Updates

This public repository only distributes **signed EXPA Client updates**. It contains no source code.

```
stable/manifest.json       update manifest of the "stable" channel (versions, URLs, sizes, SHA-256)
stable/manifest.json.sig   Ed25519 signature of manifest.json
```

Binaries (EXPA client mod jars per Minecraft version and the Windows launcher zip) are attached to this
repository's **Releases** (`vX.Y.Z`), never committed.

The EXPA launcher downloads `stable/manifest.json` and its signature, verifies the signature with the public
key compiled into the launcher, and only then downloads files — each one checked for size, SHA-256 and its
own signature. A manifest or file that fails any check is never installed.

**Do not edit `manifest.json` by hand**: any changed byte (including line endings) invalidates the signature
and every launcher will reject the update. Manifests are produced by `scripts/publish-update.ps1` in the
private source repository.

---

Bu depo yalnızca **imzalı EXPA Client güncellemelerini** dağıtır; kaynak kodu içermez. `manifest.json`
dosyasını elle düzenleme: tek bir bayt (satır sonları dahil) değişirse imza geçersiz olur ve launcher'lar
güncellemeyi reddeder.
