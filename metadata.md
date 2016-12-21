####*Droplets* can be created through the DO Control Panel or API (POST request).

#####*MetaData* is a service provided by DigitalOcean that features droplets to access data about itself. This data includes:

1. Droplet ID
2. Droplet IP
3. Datacenter region and user-data specified
4. User-data

Any action that you can perform via DO Control panel can also be performed via its API. MetaData functionality allow you to configure droplets even without logging in by specifying arbitary data in *'user-data'* section. 

*Retrieve Droplet MetaData:* You can query MetaData API by sending an HTTP GET request from your droplet to the metadata endpoint using below command:

`curl http://169.254.169.254/metadata/v1/`

Prints all available droplet metadata, those trailing by slash '/' represent *index*, while rest *data*:

```
id
hostname
user-data
vendor-data
public-keys
region
interfaces/
dns/
```

`curl http://169.254.169.254/metadata/v1/id`

Whereas, you can retrieve any specific index, say IP address via:

`curl http://169.254.169.254/metadata/v1/interfaces/public/0/ipv4/address`
