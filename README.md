### Km Invoice Helper

EPC QR Codes for ERPNext. Contrary to other implementations, we compile the necessary data points and store the resulting code as a string in the database when the invoice is saved or submitted. 

That way, no on-the-fly graphics generation breaks the scheduled creation of invoices such as in subscriptions. wkhtmldopdf will safely handle the qr code.

Turns out, payment improves with an EPC. Less mistakes are made by the payor and more correct payment references are seen even from the sloppy of accountants;). 

Tested for European Union SEPA transactions. No idea how other parts of the world deal with this, PRs welcome!

### Installation

You can install this app using the [bench](https://github.com/frappe/bench) CLI:

```bash
cd $PATH_TO_YOUR_BENCH
bench get-app git@github.com:fnznhnzn/km_invoice_helper.git --branch main
bench install-app km_invoice_helper
```
Now 
o add custom field "custom_qr_code_base64" to Sales Invoice, Text + Read Only
o add {% if doc.custom_qr_code_base64 %} <img src="{{ doc.custom_qr_code_base64 | safe }}" /> {% endif %} to Print Format


### Contributing

This app uses `pre-commit` for code formatting and linting. Please [install pre-commit](https://pre-commit.com/#installation) and enable it for this repository:

```bash
cd apps/km_invoice_helper
pre-commit install
```

Pre-commit is configured to use the following tools for checking and formatting your code:

- ruff
- eslint
- prettier
- pyupgrade

### License

mit
