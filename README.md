Setup checklist
 Zip is uploaded to a published release in a public repo
 URL contains /releases/download/
 curl.exe -IL <url> ends in 200 (not text/html)
 SHA-1 taken from the exact zip that’s uploaded, lowercase, no spaces
 Server stopped before editing server.properties
 These four keys are set:
  resource-pack=https://github.com/Jtec123/CCM-Custom-Discs/releases/download/trial/minecraft_custom_music_pack-resource-pack.zip
  resource-pack-sha1=f55c2e817848a5666b9ff6f6b996309e4673e9f1
  require-resource-pack=false
  resource-pack-prompt=Custom music discs
 Server restarted, players disconnect and rejoin

Updating the pack
Make or regenerate the new zip.
Create a new release with a new tag (v2, v3...) and upload the zip. Don’t swap the file in the old release.
Copy the new asset link (it must have the new tag in it).
Hash the new file:
   Get-FileHash -Algorithm SHA1 yourfile.zip
Lowercase it.
5. Stop the server, update both resource-pack and resource-pack-sha1, save, and start the server.
6. Players rejoin. If anyone still hears old audio, they delete the cached pack from .minecraft/server-resource-packs/ and reconnect.
