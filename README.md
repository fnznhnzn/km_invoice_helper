### Km Invoice Helper

EPC QR Codes etc.

### Installation

You can install this app using the [bench](https://github.com/frappe/bench) CLI:

```bash
cd $PATH_TO_YOUR_BENCH
bench get-app $URL_OF_THIS_REPO --branch develop
bench install-app km_invoice_helper
add custom field "custom_qr_code_base64" to Sales Invoice
add {% if doc.custom_qr_code_base64 %} <img src="{{ doc.custom_qr_code_base64 | safe }}" /> {% endif %} to Print Format
done
```

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
