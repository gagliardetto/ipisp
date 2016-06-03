# IPISP

IPISP wraps [Team Cymru's](http://www.team-cymru.org/IP-ASN-mapping.html) IP to ASN service.

IPISP allows you to programmatically resolve an IP address's AS number, ISP name, range, allocation time, registry, and country of registration.

IPISP utilizes team cymru's netcat interface so it's safe for bulk usage.

[Godoc](https://godoc.org/github.com/ammario/ipisp)

## Example

A more thorough example is in the examples/ folder.

```go
client, _ := ipisp.NewClient()
resp, err := client.LookupIP(net.ParseIP("4.2.2.2"))
   
fmt.Printf("IP: %v\n", resp.IP)
fmt.Printf("ASN: %v\n", resp.ASN)
fmt.Printf("Range: %v\n", resp.Range)
fmt.Printf("Country: %v\n", resp.Country.Name)
fmt.Printf("Registry: %v\n", resp.Registry)
fmt.Printf("ISP: %v\n", resp.Name.Raw)
```