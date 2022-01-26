# SecureCRT-Keywords
Collection of various Regular Expressions for `SecureCRT` and its wonderful Keyword Highlighting feature. Most of these should be universal but the main use case I had was for Juniper devices as that is what I work on for the most part.

This is a work in progress over time and is updated as the need arises or I find the time to write out the explinations. The one thing I've found is there are many ways to skin the Regular Expressions cat to get the desired effect. I try to make them in a way that they don't create random character highlights that I do not want.


# Appliance Info Related

**Highlight OS Version**
```
\b(?:Junos:|JUNOS) [^a-zA-Z][0-9a-zA-Z.-]*\b
```
- `\b`             assert position at a word boundary
- Non-capturing group `(?:Junos:|JUNOS)`
- 1st Alternative `Junos:`
- `Junos:`         matches the characters `Junos:` literally (case sensitive)
- 2nd Alternative `JUNOS`
- `JUNOS`          matches the characters `JUNOS` literally (case sensitive)
- `[^a-zA-Z]`      match a single character not present in the list `[^a-zA-Z]`
- `[0-9a-zA-Z.-]`  match a single character present in the list `[0-9a-zA-Z.-]`
- `*`              matches the previous token between zero and unlimited times, as many times as possible, giving back as needed (greedy)
- `.-`             matches a single character in the list `.-` (case sensitive)
- `\b`             assert position at a word boundary

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
- `[.]`     match a single character present in the list `[.]`
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
- `\b`      assert position at a word boundary
- Non-capturing group `(?:up|Up|UP)`
- 1st Alternative `up`
- `up`      matches the characters `up` literally (case sensitive)
- 2nd Alternative `Up`
- `Up`      matches the characters `Up` literally (case sensitive)
- 3rd Alternative `UP`
- `UP`      matches the characters `UP` literally (case sensitive)
- `\b`      assert position at a word boundary

**Down**
```
\b(?:down|Down|DOWN)\b
```
- `\b`      assert position at a word boundary
- Non-capturing group `(?:down|Down|DOWN)`
- 1st Alternative `down`
- `down`      matches the characters `down` literally (case sensitive)
- 2nd Alternative `Down`
- `Down`      matches the characters `Down` literally (case sensitive)
- 3rd Alternative `DOWN`
- `DOWN`      matches the characters `DOWN` literally (case sensitive)
- `\b`      assert position at a word boundary

**Port description xxxx**
```
(:?description) [a-zA-Z0-9_-]*
```
- 1st Capturing Group `(:?description)`
- `:`              matches the character `:` literally (case sensitive)
- `description`    matches the characters description literally (case sensitive)
- `[a-zA-Z0-9_-]`  match a single character present in the list `[a-zA-Z0-9_-]`
- `*`              matches the previous token between zero and unlimited times, as many times as possible, giving back as needed (greedy)
- `_-`             matches a single character in the list `_-` (case sensitive)

# IP Addresses

**ipv4 address/subnet**
```
\b(?<!\.)((25[0-5]|(2[0-4]|[0-1]?\d)?\d)\.){3}(25[0-5]|(2[0-4]|[0-1]?\d)?\d)(/\d+)?(?!\.)\b
```

**ipv6 address/subnet**
```
\s*((([0-9A-Fa-f]{1,4}:){7}([0-9A-Fa-f]{1,4}|:))|(([0-9A-Fa-f]{1,4}:){6}(:[0-9A-Fa-f]{1,4}|((25[0-5]|2[0-4][0-9]|1[0-9][0-9]|[1-9]?[0-9])(\.(25[0-5]|2[0-4][0-9]|1[0-9][0-9]|[1-9]?[0-9])){3})|:))|(([0-9A-Fa-f]{1,4}:){5}(((:[0-9A-Fa-f]{1,4}){1,2})|:((25[0-5]
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

# Routing Related
**source-address xxxx**
```
(source-address [\/a-zA-Z0-9\._-]+)?
```

**destination-address xxxx**
```
(destination-address [\/a-zA-Z0-9\._-]+)?
```
