### ripple-feration-python
---
https://github.com/miracle2k/ripple-federation-python

```py
CORS = {}

from .ripple_federation import Federation, get_ripple_txt
federation = Federation({
  '': {},
})

@expose('/ripple.txt')
def ripple_txt(request):
  return Response(get_ripple_txt(
    domain=request.host,
    federation_url='https://{}{}'.format(
      request.host, request.urlmap.build('ripple_federation'))
  ),
  mimetype='text/plain',
  headers=CORS)

@expose('/ripple/federation')
def ripple_federation(request):
  return Response(
    json.dumps(federation.endpoint(request.args)),
    mimetype='application/json',
    headers=CORS
  )

def lookup_user(domain, user):
  ripple, destination_tag = findUser(domain, user)
  return {
    'destination_address': app.config['PAYMENT_ADDRESS'],
    'dt': int(user)
  }

federation = Federation({
  'elsdoerfer.name': lookup_user,
  'elsdoerfer.name': {'micheal': callable_allowed_here_as_well},
})
```

```
```

```
```

