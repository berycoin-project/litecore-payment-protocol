Berycore Payment Protocol
=======

[![NPM Package](https://img.shields.io/npm/v/bitcore-payment-protocol.svg?style=flat-square)](https://www.npmjs.org/package/bitcore-payment-protocol)
[![Build Status](https://img.shields.io/travis/bitpay/bitcore-payment-protocol.svg?branch=master&style=flat-square)](https://travis-ci.org/bitpay/bitcore-payment-protocol)
[![Coverage Status](https://img.shields.io/coveralls/bitpay/bitcore-payment-protocol.svg?style=flat-square)](https://coveralls.io/r/bitpay/bitcore-payment-protocol)

A module for [berycore](https://github.com/berycoin-project/berycore) that implements [Payment Protocol](https://github.com/bitcoin/bips/blob/master/bip-0070.mediawiki) and other related BIPs.

## Getting Started

This library is distributed in both the npm and bower packaging systems.

```sh
npm install berycore-lib
npm install berycore-payment-protocol
```

```sh
bower install berycore-lib
bower install berycore-payment-protocol
```

There are many examples of how to use it on the developer guide [section for payment protocol](https://bitcore.io/api/paypro). For example, the following code would verify a payment request:

```javascript
var PaymentProtocol = require('berycore-payment-protocol');

var body = PaymentProtocol.PaymentRequest.decode(rawbody);
var request = new PaymentProtocol().makePaymentRequest(body);

var version = pr.get('payment_details_version');
var pki_type = pr.get('pki_type');
var pki_data = pr.get('pki_data');
var serializedDetails = pr.get('serialized_payment_details');
var signature = pr.get('signature');

// Verify the signature
var verified = request.verify();
```

## Contributing

See [CONTRIBUTING.md](https://github.com/bitpay/bitcore/blob/master/CONTRIBUTING.md) on the main bitcore repo for information about how to contribute.

## License

Code released under [the MIT license](https://github.com/berycoin-project/berycore/blob/master/LICENSE).

Copyright 2013-2015 BitPay, Inc. Bitcore is a trademark maintained by BitPay, Inc.
