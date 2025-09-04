# dopalos Scoop Bucket

## Install
powershell
scoop bucket add dopalos https://github.com/dopalos/scoop-bucket
scoop install thomasd


## Verify release

```powershell
$repo="dopalos/thomasd"; $tag="v0.1.20"
gh release download $tag -R $repo -p "SHA256SUMS.txt" -p "SHA256SUMS.txt.sig" -p "cosign.pub" --clobber
cosign verify-blob --key .\cosign.pub --signature .\SHA256SUMS.txt.sig .\SHA256SUMS.txt
# (옵션) sha256sum -c SHA256SUMS.txt
