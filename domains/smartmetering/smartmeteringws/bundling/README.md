<!--
SPDX-FileCopyrightText: Contributors to the Documentation project

SPDX-License-Identifier: Apache-2.0
-->

# Bundle

You can combine multiple requests to a meter in a bundle by creating a BundleRequest with one or more Actions in the namespace [http://www.opensmartgridplatform.org/schemas/smartmetering/sm-bundle/2014/10](http://www.opensmartgridplatform.org/schemas/smartmetering/sm-bundle/2014/10). Each Action contains one of the existing requests to a meter.

A bundle is executed using one connection to the meter. A bundle response contains all individual responses of executed commands both successful and unsuccessful. When an individual request fails it is retried when this is useful, more precisely the bundle is retried, executing only requests that are fit for re-submission.

