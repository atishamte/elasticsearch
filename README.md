# PHP - ElasticSearch cURL Library
**Technology Supports**
- PHP 7+
- ElasticSearch 7.5+
- cURL must be enabled

A library to do the simple object operations with ElasticSearch

## Methods

```
use atishamte\ElasticSearch\ElasticSearch;
include_once 'elasticsearch.php';

// If Elastic X-Pack authentication enabled
$server = 'http://elastic:admin123@localhost:9200';

// If Elastic X-Pack authentication disabled
$server = 'http://localhost:9200';

// Name of the index
$index = 'dummydata';

// New elasticsearch object 
$e = new ElasticSearch($server);

// Setting a index to object
$e->set_index($index);
--------------------------------------------------------
// Create Index
$e->create_index($index);
--------------------------------------------------------
// Set Index
$e->set_index($index);
--------------------------------------------------------
// Check Index

// Without method chaining
$e->set_index($index);
$e->check_index();

// With method chaning
$e->set_index($index)->check_index();
$e->check_index();
--------------------------------------------------------
// Check status of Index
$e->status();
--------------------------------------------------------
// Add document in index
$e->add('person', ['name' => 'Robart']);
--------------------------------------------------------
// Get document from index
$e->get('person');
--------------------------------------------------------
// Update document in index
$e->update('person', ['doc' => ['name' => 'Robart Downy Jr']]);
--------------------------------------------------------
// Query document from index
$e->query(['match' => ['name' => 'Robart Downy Jr']]);
--------------------------------------------------------
// Count all documents in index
$e->count_all();
--------------------------------------------------------
// Delete document from index
$e->delete('person');
--------------------------------------------------------
// Delete Index
$e->delete_index();
```
