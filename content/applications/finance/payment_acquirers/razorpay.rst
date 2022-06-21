========
Razorpay
========

`Razorpay <https://razorpay.com/>`_ is an online payments provider established in India and
covering more than 100 payment methods.

.. _payment_acquirers/razorpay/configure_dashboard:

Configuration on Razorpay Dashboard
===================================

#. Log into `Razorpay Dashboard <https://dashboard.razorpay.com/>`_ and go to
   :menuselection:`Settings --> API Keys`. Generate the new keys and copy the values of the
   :guilabel:`Key Id` and :guilabel:`Secret Key` fields and save them for later.
#. | Go to :menuselection:`Settings --> Webhooks` and enter your Odoo database URL followed by
     `/payment/razorpay/webhook` in the :guilabel:`Webhook URL` text field.
   | For example: `https://example.odoo.com/payment/razorpay/webhook`.
#. Fill the :guilabel:`Secret` field with a password of your choice and save it for later.
#. Make sure  :guilabel:`refund.processed` and :guilabel:`payment.captured` checkboxes are ticked.
#. Click on :guilabel:`Save` to finalize the configuration.

.. _payment_acquirers/razorpay/configure_odoo:

Configuration on Odoo
=====================

#. :ref:`Navigate to the payment acquirer Razorpay <payment_acquirers/add_new>` and change its
   state to :guilabel:`Enabled`.
#. In the :guilabel:`Credentials` tab, fill the :guilabel:`Public Key`, :guilabel:`Secret Key`, and
   :guilabel:`Webhook Secret` with the values you saved at the step
   :ref:`payment_acquirers/razorpay/configure_dashboard`.
#. Configure the rest of the options to your liking.

.. important::
  - If you configure Odoo to capture amounts manually, make sure to set the
    :guilabel:`Manual Capture` to :guilabel:`manual` on Razorpay. Otherwise, the transaction
    would be blocked in the authorized state in Odoo. To do so, go to your Razorpay Dashboard and
    then to :menuselection:`Settings --> Configuration`.
  - After **five days**, if the transaction hasn't been captured yet, the customer has the right
    to **revoke** it.

.. seealso::
   - :doc:`../payment_acquirers`
