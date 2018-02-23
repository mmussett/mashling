# RestTrigger to EmsPublisher recipe
This recipe publishes the Rest Trigger content payload to EMS Destination as message.

## Installation
* Mashling [CLI](https://github.com/TIBCOSoftware/mashling)
* EMS [Ems](https://www.tibco.com/)

## Setup
```
git clone https://github.com/mmussett/mashling
cd mashling/recipes/RestTrigger-To-EmsPublisher
mashling create -f RestTrigger-To-EmsPublisher.json RestTrigger-To-EmsPublisher
```
## Testing

* Start EMS Broker in separate terminal.
* Start the JMS message consumer.
* Start RestTrigger-To-EmsPublisher/bin/RestTrigger-To-EmsPublisher
* Use "PUT" operation and hit the url "http://localhost:8080/trigger" with the below sample payload:

```json
{
	"category": {
		"id": 16,
		"name": "Animals"
	},
	"id": 16,
	"name": "SPARROW",
	"photoUrls": [
		"string"
	],
	"status": "sold",
	"tags": [{
		"id": 0,
		"name": "string"
	}]
}
```
* The payload content of the Rest trigger gets published to "queue.sample" Destination as message.
