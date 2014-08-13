---
layout: page
title: Testing
permalink: /testing/
---

## Continous integration

### Travis CI


## Test coverage
Coverage when it comes to testing is a measure of how complete your test suit is. Basically it's calculated as the percentage of lines of code that are executed during a single run of your test suit.

One practise is to simply not accept pull requests that drop test coverage.

### Coveralls
:gift_heart: [Coveralls.io][coveralls] is a free service (public repos) that integrates with both Travis and GitHub. Test coverage is calculated while running your test suit at Travis. In case of a pull request, Coveralls can also post a comment with the updated coverage. There's of course also a badge to emblazon your README with.


[coveralls]: https://coveralls.io/
