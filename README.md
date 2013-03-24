bangspec
========

BDD? In *my* bash?

But Why?
========

I wanted to easily test the JSON RPC interface of
[Bitcoin](https://github.com/bitcoin/bitcoin), specifically new methods
as I added them. The most straightforward to test E2E seemed to use curl
to send a JSON request and then check the response (made easier by the
fabulous [jq](http://stedolan.github.com/jq/)). Plus, I really don't
know how to use bash very well and it was a good excuse to learn.

I got it working and thought it might be neat to pull out the common
bits.

Usage
=====

    > run test/suite

This will setup the core functions used (describe, it, expect, etc.) and
then source test/spec_helper.sh before sourcing the test/suite file
which contains the spec.

Here's an example spec:

    describe "toBe"
      it "should succeed with identical strings"
      testString="foo"
      expect $testString; toBe $testString

Notes
=====

Currently I'm the only user and it's only been tested with Bash 3.2.48
on OS X 10.7.5

I don't plan on adding much to the project unless I find more use cases
or others find it particularly valuable.
