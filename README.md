### WARNING

This is a hard fork of sails-mongo to add compliance with Amazon DocumentDB and the mongodb nodejs driver v3.1. It is tested to work with node 10.15.3 and mongodb 3.1.13.

For use with sails, the main change is the configuration schema. It has been updated to reflect passing connection options as a single flat object. See the MongoDB driver documentation for details on all connection options.

```
connections:{
  production: {
    adapter: 'sails-mongo',
    url: "mongodb://localhost:27017/db",
    // OR
    host: 'localhost',
    database: 'db',
    port: 27017,
    user: null,
    password: null,

    wlNext: {
      caseSensitive: true
    },

    // mongodb connection options
    options: {
      socketTimeoutMS: 10000,
      w: 'majority',
      poolSize: 5,
      replicaSet: 'rs0',
      ssl: true,
      sslValidate: true,
      sslCA: ca,
      checkServerIdentity: false
    }
  }
}
```
