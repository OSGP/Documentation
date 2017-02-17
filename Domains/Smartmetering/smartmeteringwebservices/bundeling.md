## Bundeling

You can combine multiple requests to a meter in a bundle by creating a BundleRequest with one or more Actions in the namespace
http://www.alliander.com/schemas/osgp/smartmetering/sm-bundle/2014/10. Each Action contains one of the existing requests to a meter.

A bundle is executed using one connection to the meter. A bundle response contains all indivudual responses of executed commands
both succesful and unsuccessful. When an individual request fails it is retried when this is useful, more precisely the bundle
is retried, executing only requests that are retryable.

