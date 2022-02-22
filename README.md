# My Word Of The Day

## What is it?

Ever come across words that you have to look up the definition for, only to see it again a week later and realise you've already forgotten what it means?

Yeah, me too.

This is a service which takes words you would like to learn, and aims to sends you one at random every day in the hope the definition will stick.

What you do with the words after that is completely up to you, but I recommend trying to use the word you're sent throughout the day to really learn it.

If enabled and configured, you'll get a word delivered by email based on a cron tab schedule.

## How do I use it?

For now, My Word Of The Day is exclusively API driven (i.e. there's no front end).

The easiest, and only documented, method of running this service is using Docker. An example `docker-compose.yaml` has been provided in the root of this repository, with the required environment variables, with examples/definitions as is applicable.

### Running the service

```
docker-compose up -d
```

### Adding words

```
curl -H "Content-Type: application/json" -X POST localhost:8443/api/v1alpha1/word -d '{"word": "floccinaucinihilipilification", "custom_definition": "Estimation of worthlessness"}'
```

### Listing words

```
curl -H "Content-Type: application/json" -X GET localhost:8443/api/v1alpha1/words
```

### Deleting words

```
curl -H "Content-Type: application/json" -X DELETE localhost:8443/api/v1alpha1/word/1
```


## What's on the roadmap?

* Integration with a Dictionary API, so you can specify the word you want to keep and you'll be able to keep the definition to keep.
