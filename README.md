# Secrets Management
## Curtis Badke
### Edmonton .NET User Group Meetup (February 27th, 2018)

This is a fork of Curtis Badke's [Secrets Demo](https://github.com/edmug/SecretsDemo) that will be discussed during the [meetup](https://www.meetup.com/Edmonton-NET-User-Group/events/244383352/).  Thank you to [Curtis](https://github.com/cbadke) for presenting and [DevFacto](https://www.devfacto.com/) for supporting [Edmonton .NET User Group](http://edmug.net).

# Secrets Demo
This is a very quick and dirty demo of loading configuration for ASPNET Core app
using Azure KeyVault. Prepared for my [EDMUG](https://www.meetup.com/Edmonton-NET-User-Group/)
talk on February 27, 2018.

This demo does handle some things that you may want to consider for actual
production use such as:

* dynamically taking new values if vault secrets change (everything loads on app start)
* insecure memory considerations. secrets are loading a plain strings into the
  config dictionary. if an attacker could get a memory dump of the application
  then the secrets will be easily retrievable. if this is a consideration for your
  app then other mechanisms such as SecureString should be considered.
