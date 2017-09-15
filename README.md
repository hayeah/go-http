Fork of the standard net/http package.

Some http servers care about the order of the header fields, presumably as an anti-bot protection.

This package extends the standard http package with `FixHeaderNamesOrder`, which ensures that the specified header names are output in the order you specified.

# Usage

Replace all `net/http` with `github.com/hayeah/go-http`.

Then:

the first way

```
http.FixHeaderNamesOrder([]string{"A", "B", "C"})
```
A, B, C would be output in that order, followed by all other header names in lexical order.

OR

the second way

```
header := make(http.Header)
header[DamnHeaderFieldsOrder] = []string{"B", "C", "A"}
```

B, C, A would be output in that order, followed by all other header names in lexical order.

**important: the second way's priority is higher**


