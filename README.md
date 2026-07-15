# test_lab


```
export default async function () {
  const response = await fetch(
    '/platform/classic/environment-api/v2/settings/objects?schemaIds=builtin:davis.anomaly-detectors&fields=objectId,value,modifiedBy&pageSize=500'
  );
  const data = await response.json();
  const detectors = data.items.map(item => ({
    id: item.objectId,
    title: item.value.title,
    actorId: item.modifiedBy
  }));
  return detectors;
}
```
