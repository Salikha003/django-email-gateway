

Introduction:
=============

A Simple Django app to easily send emails, receive inbound emails from users with different email vendors like AWS SES, Sendgrid, Mailgun.


Django email gateway is used for sending mails from your verified domains. It can be used to send emails from different email vendors like (AWS SES, Sendgrid, MailGun). Using this app, we can easily use different email vendors to verified, non-verified users.


Installation Procedure
======================

1. Use **pip** to install easily with one step::

      $ pip install django-email-gateway


2. Pull the code from **github** using the following command::

      git clone git://github.com/Salikha003/django-email-gateway.git

      cd django-email-gateway

      python setup.py install


Configuration
==============

- After installing/cloning the django app, add the following details in settings file to setup your email vendor for verified & non-verified users:

  .. code:: shell

      MAIL_SENDER = 'AMAZON' | 'SENDGRID' | 'MAILGUN'
      INACTIVE_MAIL_SENDER = 'AMAZON' | 'SENDGRID' | 'MAILGUN'

- If you're using **Amazon** as a email vendor, add the following settings with their values:

  .. code:: shell

    AWS_ACCESS_KEY_ID = "Your AWS Access Key"

    AWS_SECRET_ACCESS_KEY = "Your AWS Secret Key"

- If you're using **Sendgrid** as a email vendor, add the following settings with their values:

  .. code:: shell

    SG_USER = "Your Sendgrid Username"
    SG_PWD = "Your Sendgrid Password"

- If you're using **Mailgun** as a email vendor, add the following settings with their values:

  .. code:: shell

    MGUN_API_URL = "Your MailGun Api Url"
    MGUN_API_KEY = "Your MailGun Api Key"


How It Works?
=============


- Sending Emails:

  You can easily send emails to verified and non-verified users from different email vendors like AWS SES, Sendgrid, Mailgun.
  With **sending_mail** function, you can send custom emails to users. By default, it'll send emails from sendgrid. Based on user verification, it will send emails to users from the specified email vendor.

- Receiving Email:

  You can easily get the receving emails from different vendors like sendgrid, aws ses, mailgun, by configuring and veririfying your website records in the specified email vendors like SES.

  Now It supports only ses for receiving emails, we'll release a version to support sendgrid, mailgun.



How To Use:
===========

1. Add these settings to send & receive emails from different vendors.


1. **Sending email**::

      sending_mail(subject, email_template_name, context, from_email, to_email, verified)

2. **Receiving emails**::

    from django_email_gateway.receiving_mail import sns_notification
    subject, from_mail, to_mail, hash_code, mail_content = sns_notification(request.body)


It will process your message content, will return the email subject, from mail, to email(abc@yourdomain.com), hashcode(abc), mail content.

Visit our Django web development page `Here`_

