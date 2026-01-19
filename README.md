# dns-documentation
How actually the dns works?

## Authoritative DNS Server

An **authoritative DNS server** is the trusted endpoint that stores original DNS records, provides final answers, and enables delegation within the hierarchical DNS system.

### What is an Authoritative DNS Server?

An authoritative DNS server is a server that has the original source of truth for DNS records of a particular domain. Unlike recursive DNS servers that cache and forward queries, authoritative servers hold the definitive records for the domains they serve.

### Key Characteristics

1. **Trusted Endpoint**: Authoritative DNS servers are the official source of DNS information for their domains. They store the original DNS records as configured by domain administrators.

2. **Final Answers**: When queried, authoritative DNS servers provide definitive responses rather than cached or forwarded information. These responses carry the "authoritative answer" flag (AA bit) in the DNS protocol.

3. **Hierarchical Delegation**: Authoritative DNS servers enable the hierarchical structure of DNS through delegation:
   - Root nameservers delegate to Top-Level Domain (TLD) servers
   - TLD servers delegate to second-level domain servers
   - Domain servers can further delegate to subdomains

### How It Works

When a DNS query reaches an authoritative server for a domain it manages:
- It responds with the exact DNS records (A, AAAA, MX, TXT, etc.) configured for that domain
- The response includes the authoritative flag indicating it's the official answer
- If the query is for a subdomain that has been delegated, it returns NS records pointing to the authoritative servers for that subdomain

### Types of DNS Records Stored

Authoritative DNS servers typically store various record types including:
- **A records**: IPv4 addresses
- **AAAA records**: IPv6 addresses
- **MX records**: Mail server information
- **NS records**: Nameserver delegation
- **TXT records**: Text information (often used for verification)
- **CNAME records**: Canonical name aliases
- **SOA records**: Start of Authority information
