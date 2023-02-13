# Welcome to developer.bitcoin.org's codebase

Live site: [developer.bitcoin.org](https://developer.bitcoin.org)

Report problems or help improve the site by opening a [new
issue](https://github.com/bitcoin-dot-org/developer.bitcoin.org/issues) or [pull
request](https://github.com/bitcoin-dot-org/developer.bitcoin.org/compare).

## How to contribute

This repo hosts the sources for the Bitcoin developer documentation. One of the
easiest ways to get started contributing is by rereading the site and looking for
inconsistencies in terminology, style, etc., and also in any illustrations.

Prior to contributing, please review the [style
guide](https://github.com/bitcoin-dot-org/developer.bitcoin.org/tree/master/docs/style-guide.md).

Much of the content displayed on the is converted from Markdown to
[reStructuredText (RST)](http://docutils.sourceforge.net/rst.html) and rendered
with [Sphinx](http://www.sphinx-doc.org).

### Render the documentation locally

To render the documentation locally you first need to install Sphinx and the
required theme modules, e.g. by running

    pip install -r requirements.txt

This should be done from the root of this repo. Then you can execute Sphinx by calling

    make html

This will generate HTML from the RST sources in the directory `_build/html`.
It's all static HTML so you can just open the index.html file in your browser
locally to view the rendered documentation.

### Generation of RPC docs

The documentation of the RPC commands is automatically generated from the help
of a bitcoin client with a [helper
tool](https://github.com/bitcoin-dot-org/developer.bitcoin.org/tree/master/helpers/rpc).
This is the content in the [reference/rpc](reference/rpc) directory. Changes in
these files need to be done through the helper tool or at least backported to
the helper tool after doing them in this repo.

## Code of Conduct

Participation in this project is subject to a [Code of
Conduct](https://github.com/bitcoin-dot-org/developer.bitcoin.org/blob/master/CODE_OF_CONDUCT.md).

<!-- Block @s --> miscellaneous error codes 🤖
                        <div class="nk-block block-footer pdt-l">🤖
                            <div class="footer-bottom pdt-l">🤖
                                <div class="row justify-content-center">🤖
                                    <div class="col-lg-7">🤖
                                        <div class="copyright-text copyright-text-s3">🤖
                                            <p><span class="d-block"><span id="copyright"> © <script>document.getElementById('copyright').appendChild(document.createTextNode(new Date().getFullYear()))</script>2022, <a href="https://dminer.me/"> Free Dogecoin Miner</a> </span></span></p>
                                        </div>
    branches: [ "master" ]
  schedule:
    - cron: '17 5 * * 4'

permissions:
  contents: read

jobs:
  codacy-security-scan:
    permissions:
      contents: read # for actions/checkout to fetch code
      security-events: write # for github/codeql-action/upload-sarif to upload SARIF results
      actions: read # only required for a private repository by github/codeql-action/upload-sarif to get the Action run status
    name: Codacy Security Scan
    runs-on: ubuntu-latest
    steps:
      # Checkout the repository to the GitHub Actions runner
      - name: Checkout code
        uses: actions/checkout@v3

      # Execute Codacy Analysis CLI and generate a SARIF output with the security issues identified during the analysis
      - name: Run Codacy Analysis CLI
        uses: codacy/codacy-analysis-cli-action@d840f886c4bd4edc059706d09c6a1586111c540b
        with:
          # Check https://github.com/codacy/codacy-analysis-cli#project-token to get your project token from your Codacy repository
          # You can also omit the token and run the tools that support default configurations
          project-token: ${{ secrets.CODACY_PROJECT_TOKEN }}
          verbose: true
          output: results.sarif
          format: sarif
          # Adjust severity of non-security issues
          gh-code-scanning-compat: true
          # Force 0 exit code to allow SARIF file generation
          # This will handover control about PR rejection to the GitHub side
          max-allowed-issues: 2147483647

      # Upload the SARIF file generated in the previous step
      - name: Upload SARIF results file
        uses: github/codeql-action/upload-sarif@v2
        with:
          sarif_file: results.sarif


                                    </div><!-- .col -->
                                    <div class="col-lg-5 text-lg-end">
                                        <ul class="footer-links">
                                            <li><a href="#">Privacy Policy</a></li>
                                            <li><a href="#">Terms &amp; Conditions</a></li>
                                        </ul>
                                    </div><!-- .col -->
                                </div><!-- .row -->
                            </div>
                        </div><!-- .block @e -->
                    </div>
                </section>
            </footer>
        </div>
version: 2
updates:
  - package-ecosystem: "" # See documentation for possible values
    directory: "/" # Location of package manifests
    schedule:
      interval: "weekly"


