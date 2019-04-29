[![Gravity Department](https://cdn.gravitydept.com/github/repo-header.png)](https://gravitydept.com/)

# Magento Release Diffs

Useful release diffs for Magento (without copyright changes).

## Backstory

Magento does not provide usable DIFF files for new releases. Every year the copyright text changes, which makes the diff completely unusable (10,000+ vs 200 changes).

More info: http://gravitydept.com/blog/usable-release-diffs-for-magento

## Purpose

This project normalizes the copyright changes between Magento releases, and provide a diff containing only legitimate changes.

## Process to create a diff file

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

## Release Coverage

### Magento 1

GravDept is committed to producing new diffs for Magento 1 until it's unsupported. I went backward several years to 1.8.x then stopped. There shouldn't be stores older than that in the wild, but if a need presents itself I'll go back further.

Note: Magento Enterprise is not covered because I don't want to poke the bear.

### Magento 2

Note: initially I'm focused on M1, but I'd like to produce comparable diffs for all M2 releases.

## Contributing

Contributions are welcome. Please follow the same process and formatting for consistency.
