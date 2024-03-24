`for i in *.7z; do mkdir "${i%%}.7z"; 7z e -o"$i" "${i%%}.7z"; done`

`for i in *.7z; do 7z e "$i" -o"${i%%.7z}"; done`
