# information-diet

Aggregating the content I've consumed.

## Mechanism

- Fetch data from Pocket/scrape data from Goodreads
- Parse and format
- Write to an S3 bucket that has public read access

## Pocket

Use [this tool](https://reader.fxneumann.de/plugins/oneclickpocket/auth.php) by
[Felix Neumann](https://twitter.com/fxneumann) to get a long-lived access token using the annoying three-legged OAuth
flow.

## Goodreads

The Goodreads API no longer accepts signups 🥲, so I'm using
[Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/) to scrape my Goodreads "read" shelf.

This will break at some point.

## Secrets

Stored as GitHub Actions secrets.

```yaml
# implicitly used by AWS Terraform provider
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY

# explicitly declared in infra/variables.tf
AWS_ACCOUNT_NUMBER
POCKET_CONSUMER_KEY
POCKET_ACCESS_TOKEN
```
