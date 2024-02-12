[[COMP35112]]

- note that ==all cores must see invalidates/updates at the same time== i.e. within the same bus cycle
# write-invalidate

- when a core updates a cache line, other copies of that line in other caches are ==invalidated==
- future accesses from other caches will require fetching the update lines from other caches/memory
- most widespread protocol, used [[MSI cache states|MSI]], [[MESI protocol|MESI]]

# write-update

- when a core updates a cache line, the modification itself is broadcast to copies of that line in other caches - they are ==updated==
- this leads to higher bus traffic in comparison to write-invalidate
- example protocols: dragon, firefly