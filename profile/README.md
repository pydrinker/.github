# pydrinker

The most amazing lib to drink (consume) message from your queue provider of preference.

# pydrinker and its layers

This project have layers to make pydrinker works fine, let's explain about layers and libraries:

- [pydrinker-loafer](https://github.com/pydrinker/pydrinker-loafer): This is where the project starts, based on [olist-loafer](https://github.com/olist/olist-loafer) the unique difference between olist-loafer and pydrinker-loafer is about dependencies with [aiobotocore](https://github.com/aio-libs/aiobotocore), pydrinker-loafer doesn't have this dependency;

- [pydrinker](https://github.com/pydrinker): This is a abstraction layer between pydrinker-loafer and all pydrinker libs, this project makes possible change thinks of original loafer project, the future of this project is switch all core structure to here and remove pydrinker-loafer;

- [pydrinker-gcp](https://github.com/pydrinker-gcp): This is a extension of pydrinker for Google Cloud Provider to make pydrinker consume messages from [GCP Subscribers](https://cloud.google.com/pubsub/docs/subscriber);

- `pydrinker-<provider>`: For future! We have N possibilities to create consumers for infinite providers.

# Support

## Providers
- [x] Google Cloud Provider
- [ ] Amazon SQS
- [ ] ... what do you need? :smile:

## Python version
- [ ] 3.7.x
- [ ] 3.8.x
- [x] 3.9.x
- [ ] 3.10.x

# How to create my first Google Cloud Provider consumer?

1. Create a virtualenv and install:

```
python3 -m venv .venv
source .venv/bin/activate
pip install pydrinker[gcp]
```

2. Create a Google Service Account and download the `credential.json` [described here](https://cloud.google.com/iam/docs/creating-managing-service-accounts#iam-service-accounts-create-console).

3. Create a topic and a subscription to make consumer consume this message, you can see [more here](https://cloud.google.com/pubsub/docs/publisher). 

4. Download the file [one_file_gcp_consumer.py](https://raw.githubusercontent.com/pydrinker/pydrinker/main/samples/one_file_gcp_consumer.py) to your path, activate your venv (if necessary) and run like below:
```
GOOGLE_APPLICATION_CREDENTIALS="credential.json" python one_file_gcp_consumer.py
```
5. When you receive a message the output should be like below:
```
Let's consume a message!
message, {'teste': 123}
args, ({'ack_id': 'somelongandweirdcode', 'message_id': '3244373101714015', 'publish_time': DatetimeWithNanoseconds(2021, 10, 20, 15, 18, 43, 831000, tzinfo=datetime.timezone.utc), 'ordering_key': '', 'attributes': {}},)
```

A complete version is available on [simple-gcp-consumer](https://github.com/pydrinker/simple-gcp-consumer).

# Credits

- All commiters of [loafer](https://github.com/georgeyk/loafer) and [olist-loafer](https://github.com/olist/olist-loafer) projects deserve a lot of credit, because without them this project/idea would not exist;

- [@jusbrasil](https://github.com/jusbrasil/) to give me the freedom to work with this open source project.

Thanks for that!
