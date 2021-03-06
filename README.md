# PagerDuty Operational Review Documentation [![Build Status](https://circleci.com/gh/PagerDuty/operational-review-docs/tree/master.svg?style=svg)](https://circleci.com/gh/PagerDuty/operational-review-docs)
This is a public version of the Operational Review framework that PagerDuty is adapting and implementing internally. It is used to ensure that PagerDuty leadership is aligned on the impact that real-time, digital operations have on our business outcomes. See the [About](/docs/about.md) page for more information.

You can view the documentation [directly](/docs/index.md) in this repository, or rendered as a website at https://reviews.pagerduty.com.

[![Operational Reviews](screenshot.png)](https://reviews.pagerduty.com)

## Development Info
We use [MkDocs](http://www.mkdocs.org/) to create a static site from this repository. For local development,

1. Install v0.1.1 of [MKDocs Bootstrap](https://github.com/mkdocs/mkdocs-bootstrap) `pip install mkdocs-bootstrap==0.1.1`
1. Install v0.1.0 of [MkDocs Bootswatch theme](https://github.com/mkdocs/mkdocs-bootswatch)`pip install mkdocs-bootswatch==0.1.0`
1. Install v0.15.3 of [MkDocs](http://www.mkdocs.org/#installation). `pip install mkdocs==0.15.3`
1. Install v0.2.4 of the [MkDocs Material theme](https://github.com/squidfunk/mkdocs-material). `pip install mkdocs-material==0.2.4`
1. To test locally, run `mkdocs serve` from the project directory.

## Deploying
1. Run `mkdocs build --clean` to produce the static site for upload.
1. Upload the `site` directory to S3 (or wherever you would like it to be hosted).

        aws s3 sync ./site/ s3://[BUCKET_NAME] \
          --acl public-read \
          --exclude "*.py*" \
          --delete

## License
[Apache 2](http://www.apache.org/licenses/LICENSE-2.0) (See [LICENSE](LICENSE) file)

## Contributing
Thank you for considering contributing! If you have any questions, just ask - or submit your issue or pull request anyway. The worst that can happen is we'll politely ask you to change something. We appreciate all friendly contributions.

Here is our preferred process for submitting a pull request,

1. Fork it ( https://github.com/PagerDuty/operational-review-docs/fork )
1. Create your feature branch (`git checkout -b my-new-feature`)
1. Commit your changes (`git commit -am 'Add some feature'`)
1. Push to the branch (`git push origin my-new-feature`)
1. Create a new Pull Request.
