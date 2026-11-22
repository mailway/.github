<picture>
  <source media="(prefers-color-scheme: dark)" srcset="mailway-banner-dark.svg">
  <img src="mailway-banner-light.svg" alt="Mailway: Keep every email your app sends." width="100%">
</picture>

Mailway sits between your app and the email providers you already use. It keeps every email as it received it and shows what happened to each one, and if a provider refuses a mail, it sends it through the next.

- **Sent folder:** the archive of every email your app sends, kept as Mailway received it and searchable.
- **Delivery history:** for each mail, every provider attempt and answer, and the delivery events the provider reported.
- **Proof of delivery:** once a provider accepts a mail, a signed certificate of what was sent and when, with the delivery event if the provider reported one. It verifies offline with standard tools.
- **Automatic failover:** if a provider refuses a mail, the next provider you set up sends it.

Proof of delivery and automatic failover are not on every plan: [see which plans include them](https://mailway.net/docs/plans).

Mailway is not an email provider. You bring your own provider accounts (for example Amazon SES, SendGrid, Mailgun, or Postmark), and Mailway sends through them. Mail is received, routed, and archived in the EU, all in Germany: Mailway's servers run at Hetzner in Falkenstein, and archived messages are stored in AWS S3 in Frankfurt.

## Send through Mailway

If your app already sends over SMTP, switching is a configuration change. Create an SMTP credential for your project in the console (the [SMTP quickstart](https://mailway.net/docs/quickstart) shows how), then set:

```ini
SMTP_HOST=smtp.mailway.net
SMTP_PORT=587
SMTP_USERNAME=mw_user_…
SMTP_PASSWORD=mw_pass_…
SMTP_ENCRYPTION=tls   # STARTTLS
```

To send JSON over HTTPS instead, use the [HTTP API](https://mailway.net/docs/api/send) with an API key.

## Status

Mailway is in private beta, and we onboard teams one at a time. [Join the waitlist](https://mailway.net/#waitlist) and we'll email your invite, or [see the demo](https://mailway.net/demo) first.

## Links

- [Documentation](https://mailway.net/docs) and the [SMTP quickstart](https://mailway.net/docs/quickstart)
- [Trust and security](https://mailway.net/trust): where Mailway runs, and its sub-processors
- [Service status](https://status.mailway.net)
- Questions: [hello@mailway.net](mailto:hello@mailway.net)
- Security reports: [security@mailway.net](mailto:security@mailway.net) (see [SECURITY.md](https://github.com/mailway/.github/blob/main/SECURITY.md))
