# Magento Release Diffs

Release diffs for Magento (minus copyright changes).

A frustrating project from:

[![Gravity Department](http://gravitydept.com/_themes/gravdept/img/logo-footer.png)](http://gravitydept.com/)

## Problem

Magento does not provide usable DIFF files for new releases. Every year the copyright text changes, which makes the diff completely unusable (10,000+ vs 200 changes).

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Raise a glass to my 9th year pointing out <a href="https://twitter.com/magento?ref_src=twsrc%5Etfw">@magento</a> changing copyright in every file once a year costs thousands of non-productive hours.<br><br>The release diff has 9251 changes like this. Everyone has to individually decipher what actually changed. <a href="https://t.co/XDS69fJsfF">pic.twitter.com/XDS69fJsfF</a></p>&mdash; Brendan Falkowski (@Falkowski) <a href="https://twitter.com/Falkowski/status/968941703926198272?ref_src=twsrc%5Etfw">February 28, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

## Purpose

This project normalizes the copyright changes between Magento releases, and provide a diff containing only legitimate changes.

## Could Magento solve this?

Yes. They could choose not to change their copyright text annually. Or they could publish a release on January 1 with copyright changes only. They have a process problem, and it's been annoying since 2009.

Fixing it would free every individual developer from needing to generate a legitimate diff. We're collectively wasting thousands of hours to decipher releases afflicted by copyright changes.

## How to create a diff file

1. Download the target and preceding release of Magento.
1. Create an Git repo.
1. Commit the older release.
1. Delete all those files.
1. Copy the newer release into the repo.
1. Look for insignificant copyright changes across all files.
1. Find/replace to normalize all the copyright differences.
1. Commit the new release.
1. Run the following command:

``` bash
git diff --name-status [commit1] [commit2] > [oldRelease]___[newRelease].txt
```

Add the following header text to the file:

```

RELEASE DIFF
Magento Community [oldRelease] — [newRelease]
https://github.com/gravitydepartment/magento-release-diffs

// ----------------------------------------------

```

## Contributing

Contributions are welcome. Please follow the same process / formatting for consistency.
