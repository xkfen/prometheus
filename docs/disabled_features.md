---
title: Disabled Features
sort_rank: 10
---

# Disabled Features

Here is a list of features that are disabled by default since they are breaking changes or are considered experimental.
Their behaviour can change in future releases which will be communicated via the [release changelog](https://github.com/prometheus/prometheus/blob/main/CHANGELOG.md).

You can enable them using the `--enable-feature` flag with a comma separated list of features.
They may be enabled by default in future versions.

## `@` Modifier in PromQL

`--enable-feature=promql-at-modifier`

The `@` modifier lets you specify the evaluation time for instant vector selectors,
range vector selectors, and subqueries. More details can be found [here](querying/basics.md#modifier).

## Negative offset in PromQL

This negative offset is disabled by default since it breaks the invariant
that PromQL does not look ahead of the evaluation time for samples.

`--enable-feature=promql-negative-offset`

In contrast to the positive offset modifier, the negative offset modifier lets
one shift a vector selector into the future.  An example in which one may want
to use a negative offset is reviewing past data and making temporal comparisons
with more recent data.

More details can be found [here](querying/basics.md#offset-modifier).

## Remote Write Receiver

`--enable-feature=remote-write-receiver`

The remote write receiver allows Prometheus to accept remote write requests from other Prometheus servers. More details can be found [here](storage.md#overview).

