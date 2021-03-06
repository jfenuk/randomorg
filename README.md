randomorg
=========

Random generator via athmospehric noise [Random.org](http://random.org)

**Implementation**

All work with HTTP GET API happens in **HttpWork** util class. As we do not know
return type for concrete GET-request yet we return **BufferedReader** which
can be handled in idiomatic *while-readLine-not-null* way.

All methods returns BufferedReader is server response code 200.
In case server returns 503 response code, IOException is thrown and should be
handled on client side.

Read javadoc for full method information. Simple usage:

**Integer Generator**

    // generate two 6-side dice rolls
    IntegerGenerator ig = new IntegerGenerator();
    ig.generate(1,6,2)

**Sequence Generator**

    // shuffle 52-card deck
    SequenceGenerator sg = new SequenceGenerator();
    sg.generate(1, 52);

**String Generator**

    // new password alphanumeric 12 chars
    StringGenerator strg = new StringGenerator();
    strg.generate(12, 1, true, true, true, true);

**Quota Checker**

    // check your remaining quota
    QuotaChecker qc = new QuotaChecker();
    qc.quota();
