# SecureCRT-Keywords
Collection of various Regular Expressions for SecureCRT Keyword Highlighting


# IP Addresses


**ipv4 address/subnet**
```
\b(?<!\.)((25[0-5]|(2[0-4]|[0-1]?\d)?\d)\.){3}(25[0-5]|(2[0-4]|[0-1]?\d)?\d)(/\d+)?(?!\.)\b
```


**ipv6 address/subnet**
```
\s*((([0-9A-Fa-f]{1,4}:){7}([0-9A-Fa-f]{1,4}|:))|(([0-9A-Fa-f]{1,4}:){6}(:[0-9A-Fa-f]{1,4}|((25[0-5]|2[0-4][0-9]|1[0-9][0-9]|[1-9]?[0-9])(\.(25[0-5]|2[0-4][0-9]|1[0-9][0-9]|[1-9]?[0-9])){3})|:))|(([0-9A-Fa-f]{1,4}:){5}(((:[0-9A-Fa-f]{1,4}){1,2})|:((25[0-5]
```

# Appliance Ports


**ae/ge/xe ports**
```
[agx]e-\d\D\d\D\d*[.]?\d*
```
- `[agx]`   matches a single character in the list `agx` (case sensitive)
- `e-`      matches the characters `e-` literally (case sensitive)
- `\d`      matches a digit (equivalent to `[0-9]`)
- `\D`      matches any character that's not a digit (equivalent to `[^0-9]`)
- `\d`      matches a digit (equivalent to `[0-9]`)
- `\D`      matches any character that's not a digit (equivalent to `[^0-9]`)
- `\d`      matches a digit (equivalent to `[0-9]`)
- `*`       matches the previous token between zero and unlimited times, as many times as possible, giving back as needed (greedy)
- `[.]`     match a single character present in the list below `[.]`
- `?`       matches the previous token between zero and one times, as many times as possible, giving back as needed (greedy)
- `\d`      matches a digit (equivalent to `[0-9]`)
- `*`       matches the previous token between zero and unlimited times, as many times as possible, giving back as needed (greedy)

**st0.xx**
```
st0[.]?\d*
```
- `st0`     matches the characters `st0` literally (case sensitive)
- `[.]`     match a single character present in the list below `[.]`
- `?`       matches the previous token between zero and one times, as many times as possible, giving back as needed (greedy)
- `\d`      matches a digit (equivalent to `[0-9]`)
- `*`       matches the previous token between zero and unlimited times, as many times as possible, giving back as needed (greedy)

**lo0.xxx**
```
lo0[.]?\d*
```
- `lo0`     matches the characters `lo0` literally (case sensitive)
- `[.]`     match a single character present in the list below `[.]`
- `?`       matches the previous token between zero and one times, as many times as possible, giving back as needed (greedy)
- `\d`      matches a digit (equivalent to `[0-9]`)
- `*`       matches the previous token between zero and unlimited times, as many times as possible, giving back as needed (greedy)

**Up**
```
\b(?:up|Up|UP)\b
```

**Down**
```
\b(?:down|Down|DOWN)\b
```

# Security Policy Related
**from-zone xxxx**
```
(from-zone [a-zA-Z0-9_-]+ )
```


**to-zone xxxx**
```
(to-zone [a-zA-Z0-9_-]+ )
```


**policy xxxx**
```
(policy [a-zA-Z0-9_-]+ )
```

# Port Descriptions
**description xxxx**
```
(:?description) [a-zA-Z0-9_-]*
```

# Routing Related
**source-address xxxx**
```
(source-address [\/a-zA-Z0-9\._-]+)?
```


**destination-address xxxx**
```
(destination-address [\/a-zA-Z0-9\._-]+)?
```

# Appliance Info Related

**Highlight OS Version**
```
\b(?:Junos:|JUNOS) [^a-zA-Z][0-9a-zA-Z.-]*\b
```

