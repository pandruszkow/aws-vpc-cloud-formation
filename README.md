# devops-cloudformation-simplified-privatepublic-vpc-example

This is a simplified example of how to deploy a CloudFormation template that has:
- a private subnet for private-net only machines (e.g. DB servers) that still need dial-out access to the outside world (for package updates, mostly)
- a public subnet for public-net machines (e.g. HTTPS servers) that must nonetheless speak to private machines to query data from them
- a managed NAT gateway situated in the public subnet, but it's routed so that outside-facing outbound traffic for the private subnet has to pass through it, and then out of the public subnet

deploy the DB server in the private-only subnet, and in the public subnet deploy the NAT gateway to relay the traffic and the public-net server.
