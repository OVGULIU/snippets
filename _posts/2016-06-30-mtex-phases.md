---
category: mtex
path: '/mtex/id'
title: 'Access phase names'
type: 'matlab'

layout: default
---

### Access phases present in EBSD map

```phases = ebsd.mineralList;```

this results in a cell array containing phase names as strings, e.g. 'Austenite', 'Ferrite'

### Get rid of non-indexed phases

If only 'notIndexed' phase is present in all of the datasets,

```phases = phases(~strcomp(phases,'notIndexed'));```

If two non-indexed names can be encountered, e.g. 'notIndexed' and 'not indexed', then

```phases = phases(~strcomp(phases,'notIndexed') & ~strcomp(phases,'notIndexed'));```

- `strcomp(cell_array,string)` returns logical ones for cells of the `cell_array` coinciding with the `string`.

### Return as a single string

```phaseList = strjoin(phases,', ')```
