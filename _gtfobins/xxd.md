---
functions:
  file-write:
    - code: |
        LFILE=file_to_write
        echo DATA | xxd | xxd -r - "$LFILE" 
        xxd "$LFILE" | xxd -r -s 100
  file-read:
    - code: |
        LFILE=file_to_read
        xxd "$LFILE" | xxd -r
  suid:
    - code: |
        LFILE=file_to_read
        ./xxd "$LFILE" | xxd -r
  sudo:
    - code: |
        LFILE=file_to_read
        sudo xxd "$LFILE" | xxd -r
---
