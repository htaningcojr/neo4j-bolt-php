## Neo4j Bolt PHP

PHP Driver for Neo4j's Bolt Remoting Protocol

---

### DEV MODE

This library will remain in 1.0.0-dev version until stable release of Neo4j's Bolt.

---

### Installation

Require the package in your composer dependencies :

```bash
composer require graphaware/neo4j-bolt-driver
```

Instantiate the driver by passing the host and the port to use, default port is `7687`.

```php
use GraphAware\Bolt\Driver;

$bolt = new Driver('localhost', 7687);
```

All statements need to be handled by a `Session`, getting a session is easy and will automatically trigger the
version negotiation (also called `Handshake`) :

```php
$session = $bolt->getSession();
```

Send your statements :

```php
$results = $session->run('MATCH (n:User {id: {id}}) RETURN n', array('id' => 123));
```

---

License : `MIT`

Author: `Christophe Willemsen`

---