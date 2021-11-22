# What's new in Serverless (NEXT'21)

YouTube Link from the Conf: [https://www.youtube.com/watch?v=KYBVjl6reXc](https://www.youtube.com/watch?v=KYBVjl6reXc)

## Functions
### New runtimes
- Ruby 2.6/2.7
- .NET Core 3.1
- PHP 7.4 Preview
- Python 3.9
- Node
	- 14 GA
	- 16 Preview
### Customisation in build process
- can customise build location via private pools (eg, data soverignty)
- build environment variables
- can build within VPCSC perimeter
- minimum instances in functions
	- keep 1 or more instances warm (at 10% of cost when unused!)

## Orchestration
### Event Arc
- Cloud function targets (preview)
- Native cloud storage event source (preview)
- New standalone ui (preview)

### Workflows
- HTTP callbacks with serverless waiting
- Connectors to GCP APIs
- 4x memory and 10x concurrent executions
- syntax and library enhancements

## Cloud Run
### Committed Use Discounts
- 17% discount on the amount you committed
- If you go over, it's just standard rates
- All services, all regions

### Improved developer experience
#### Local development
- Run cloud run services in a local emulator
	- Store your cloud run config
	- emulator will run your app with the memory and cpu characteristics you define
	- run with environment variables you define
	- rebuild and restart local server when changes are detected
- Available in:
	- gcloud
	- VSCode
	- CloudCode IntelliJ
	- Cloud Shell Editor

#### Deploy from local source
Improved experience, using GCP provided buildpacks, cloud build and artifact registry. Supports:
- Go 1.10+
- Node.js 10+
- Python 3.7+
- Java 8 & 11
- .NET Core 3.1+
- Dockerfile

### More observability
- Instance count
- Error reporting captures system errors
	- Max instance errors
	- Out of memory
	- etc
- Cloud Trace out of the box for requests
	- Use without any instrumentation needed

### CPU Allocation control
- CPU can optionally be always allocated, as long as the instance is alive, vs only when an active request is in flight.
	- Useful for async code
		- Goroutines
		- Node.js Async
		- Java threads
	- Telemetry support
	- Background tasks
- Different price structure.
	- No longer charged for request fees
	- CPU and Memory is 25% cheaper
	- Can be coupled with min instances

### New execution environment
- Second gen execution environment
- Increases network and CPU performance
- Full linux compatibility
- Network File System Support

### Pushing the limits of cloud run
- Websockets, HTTP/2 gRPC streaming
- 16gb ram
- 4vcpus
- 1 hour timeout
- 1,000 concurrent requests per instance
	- Useful for websockets and opening many streams

### Security
#### Regulatory Frameworks
- FedRAMP Moderate
- PCI DSS
- SOC 1, 2 and 3
- ISO27001, 27017, 27018, 27701

#### Secure perimeter
- Ingress/Egress control
	- Allow only internal traffic
	- Allow only internal + load balancer traffic
	- Force egress to go through VPC
- Put services inside a VPCSC perimeter
- Cloud Armor (via LB)
- IDAP for internal apps that are publicly facing

#### Secure services
- Native integration with Secret Manager
	- Mounted as volumes
	- or exposed as ENV VARs
- Service Identity
- Binary Authorisation
- CMEK (preview)
	- Encrypt the containers deployed to cloud run
- Pro-actively produce recommendations to secure cloud run services
	- eg, dedicated service accounts for each cloud run application with permission sets