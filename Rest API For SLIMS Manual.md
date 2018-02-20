<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Rest API For SLIMS Manual</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__left">
    <div class="stackedit__toc">
      
<ul>
<li><a href="#rest-api-for-slims-manual">Rest API For SLIMS Manual</a></li>
<li><a href="#a-idtoctable-of-contentsa">TABLE OF CONTENTS</a></li>
<li><a href="#a-idtoc1objectivesa">OBJECTIVES</a>
<ul>
<li>
<ul>
<li></li>
</ul>
</li>
</ul>
</li>
<li><a href="#a-idtoc2definitionsa">DEFINITIONS</a>
<ul>
<li></li>
</ul>
</li>
<li><a href="#a-idtoc3basic-table-operationsa">BASIC TABLE OPERATIONS</a>
<ul>
<li><a href="#update-multiple-records">Update Multiple Records</a></li>
<li><a href="#fetch-records-by-criteria">Fetch Records by Criteria</a></li>
<li><a href="#add-a-record">Add a Record</a></li>
<li><a href="#update-a-record-by-pk">Update a Record by Pk</a></li>
<li><a href="#remove-a-record-by-pk">Remove a Record by Pk</a></li>
<li><a href="#fetch-records-by-primary-key">Fetch Records by Primary Key</a></li>
<li><a href="#fetch-records-with-advanced-criteria-sorting-and-paging">Fetch Records with Advanced Criteria, Sorting, and Paging</a></li>
</ul>
</li>
<li><a href="#a-idtoc4content-linked-in-elna">CONTENT LINKED IN ELN</a>
<ul>
<li><a href="#fetch-content-linked-to-an-experiment-run-step">Fetch Content Linked to an Experiment Run Step</a></li>
<li><a href="#unlink-content-from-an-experiment-run-step">Unlink Content from an Experiment Run Step</a></li>
<li><a href="#link-content-to-an-experiment-run-step">Link Content to an Experiment Run Step</a></li>
</ul>
</li>
<li><a href="#a-idtoc5content-mix-operationa">CONTENT MIX OPERATION</a>
<ul>
<li><a href="#create-a-mix-of-ingredients">Create a Mix of Ingredients</a></li>
</ul>
</li>
<li><a href="#a-idtoc6electronic-lab-notebook-elna">Electronic Lab Notebook (ELN)</a>
<ul>
<li><a href="#fetch-root-of-eln-tree">Fetch Root of ELN Tree</a></li>
<li><a href="#fetch-children-of-a-record-in-eln-tree">Fetch Children of a Record in ELN Tree</a></li>
<li><a href="#add-a-simplified-block-to-an-experiment-run">Add a Simplified Block to an Experiment Run</a></li>
</ul>
</li>
<li><a href="#a-idtoc7external-service-controllera">External Service Controller</a>
<ul>
<li><a href="#register">Register</a></li>
<li><a href="#log">Log</a></li>
<li><a href="#status">Status</a></li>
<li><a href="#user-secret-check">User Secret Check</a></li>
</ul>
</li>
<li><a href="#a-idtoc8file-repository-operationsa">File Repository Operations</a>
<ul>
<li><a href="#upload-a-new-attachment">Upload a New Attachment</a></li>
<li><a href="#download-the-attachment">Download the Attachment</a></li>
</ul>
</li>
<li><a href="#a-idtoc9queuea">Queue</a>
<ul>
<li><a href="#fetch-record-in-queue-in-a-certain-status">Fetch Record in Queue in a Certain Status</a></li>
</ul>
</li>
</ul>

    </div>
  </div>
  <div class="stackedit__right">
    <div class="stackedit__html">
      <h1 id="rest-api-for-slims-manual">Rest API For SLIMS Manual</h1>
<p><img src="https://lh3.googleusercontent.com/2kg1HTUaqf6TvwcL12p9whv8QSKvsMOs3G4A-6cNX8cE6GOslVSWTjoh7VTESTOltYelsZdQfBkh" alt="SLIMS product logo"></p>
<p><strong>Authored by: Genohm Training Resources Team</strong><br>
<strong>Generation Date: 19-FEB-2018</strong></p>
<h1 id="a-idtoctable-of-contentsa"><a id="toc">TABLE OF CONTENTS</a></h1><a id="toc">
</a><ol><a id="toc">
</a><li><a id="toc"></a><a href="#toc1">Objectives</a></li>
<li><a href="#toc2">Definitions</a></li>
<li><a href="#toc3">Basic Table Operations</a></li>
<li><a href="#toc4">Content Linked in ELN</a></li>
<li><a href="#toc5">Content Mix Operation</a></li>
<li><a href="#toc6">Electronic Lab Notebook (ELN)</a></li>
<li><a href="#toc7">External Service Controller</a></li>
<li><a href="#toc8">File Repository Operations</a></li>
<li><a href="#toc9">Queue</a></li>
</ol>
<h1 id="a-idtoc1objectivesa"><a id="toc1"></a><a href="#toc">OBJECTIVES</a></h1>
<h4 id="version-information">VERSION INFORMATION</h4>
<p>Manual Version: 2.0 DRAFT<br>
Rest API Version:</p>
<h4 id="uri-scheme">URI SCHEME</h4>
<p>BasePath : /rest<br>
Schemes : HTTP</p>
<h4 id="preface">PREFACE</h4>
<p>This document covers the fundamental concepts for Developers using the Rest API For SLIMS to do basic database operations.  The Rest API allows Developers to interact with SLIMS without using the GUI interface to perform operations such as fetch and update of data.</p>
<h4 id="audience">AUDIENCE</h4>
<p>Developer users of the SLIMS system who will fetch information for reporting or perform update of data using external tools through API.</p>
<h4 id="assistance">ASSISTANCE</h4>
<p>To get technical assistance with the Rest API, <a href="mailto:%3Cinfo@genohm.com%3E;">contact the developer.</a></p>
<h1 id="a-idtoc2definitionsa"><a id="toc2"></a><a href="#toc">DEFINITIONS</a></h1>
<h3 id="a-iddecdisplayableentitycolumn«object»a"><a id="dec">DisplayableEntityColumn«object»</a></h3><a id="dec">

<table>
<thead>
<tr>
<th align="left">Name</th>
<th align="left">Schema</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left"><strong>editable</strong> (<em>optional</em>)</td>
<td align="left">Boolean</td>
</tr>
<tr>
<td align="left"><strong>hidden</strong> (<em>optional</em>)</td>
<td align="left">Boolean</td>
</tr>
<tr>
<td align="left"><strong>name</strong> (<em>optional</em>)</td>
<td align="left">String</td>
</tr>
<tr>
<td align="left"><strong>position</strong> (<em>optional</em>)</td>
<td align="left">Integer (int32)</td>
</tr>
<tr>
<td align="left"><strong>title</strong> (<em>optional</em>)</td>
<td align="left">String</td>
</tr>
<tr>
<td align="left"><strong>value</strong> (<em>optional</em>)</td>
<td align="left">Object</td>
</tr>
</tbody>
</table></a><h3 id="a-idderdisplayableentityresourcea"><a id="dec"></a><a id="der">DisplayableEntityResource</a></h3><a id="der">

<table>
<thead>
<tr>
<th align="left">Name</th>
<th align="left">Schema</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">canDelete (<em>optional</em>)</td>
<td align="left">Boolean</td>
</tr>
<tr>
<td align="left">canUpdate (<em>optional</em>)</td>
<td align="left">Boolean</td>
</tr>
<tr>
<td align="left">columns (<em>optional</em>)</td>
<td align="left"><a href="#dec">&lt; DisplayableEntityColumn«object» &gt;</a> array</td>
</tr>
<tr>
<td align="left">links (<em>optional</em>)</td>
<td align="left">&lt; Link &gt; array</td>
</tr>
<tr>
<td align="left">pk (<em>optional</em>)</td>
<td align="left">Integer (int64)</td>
</tr>
<tr>
<td align="left">tableName (<em>optional</em>)</td>
<td align="left">String</td>
</tr>
</tbody>
</table><h3 id="link">Link</h3>

<table>
<thead>
<tr>
<th align="left">Name</th>
<th align="left">Schema</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">href (<em>optional</em>)</td>
<td align="left">String</td>
</tr>
<tr>
<td align="left">rel (<em>optional</em>)</td>
<td align="left">String</td>
</tr>
</tbody>
</table><h3 id="model-containing-the-mix-values-and-ingredients-pks">Model containing the mix values and ingredients pks</h3>

<table>
<thead>
<tr>
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Schema</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left"><strong>ingredientsPks</strong> (<em>optional</em>)</td>
<td align="left">Ingredient Packages (Pks)</td>
<td align="left">&lt; integer (int64) &gt; array</td>
</tr>
<tr>
<td align="left"><strong>mixValues</strong> (<em>optional</em>)</td>
<td align="left">Mix values</td>
<td align="left">Object</td>
</tr>
</tbody>
</table><h3 id="represents-a-fetch-request-for-advanced-criteria">Represents a fetch request for advanced criteria</h3>

<table>
<thead>
<tr>
<th align="left">Name</th>
<th align="left">Schema</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left"><strong>criteria</strong> (<em>optional</em>)</td>
<td align="left">Object</td>
</tr>
<tr>
<td align="left"><strong>endRow</strong> (<em>optional</em>)</td>
<td align="left">Integer (int64)</td>
</tr>
<tr>
<td align="left"><strong>sortBy</strong> (<em>optional</em>)</td>
<td align="left">&lt; String &gt; array</td>
</tr>
<tr>
<td align="left"><strong>startRow</strong> (<em>optional</em>)</td>
<td align="left">Integer (int64)</td>
</tr>
</tbody>
</table><h3 id="restfetchresponse">RestFetchResponse</h3>

<table>
<thead>
<tr>
<th align="left">Name</th>
<th align="left">Schema</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left"><strong>entities</strong> (<em>optional</em>)</td>
<td align="left"><a href="#der">&lt; DisplayableEntityResource &gt;</a> array</td>
</tr>
</tbody>
</table></a><h1 id="a-idtoc3basic-table-operationsa"><a id="der"></a><a id="toc3"></a><a href="#toc">BASIC TABLE OPERATIONS</a></h1>
<h2 id="update-multiple-records">Update Multiple Records</h2>
<blockquote>
<p><strong>POST</strong></p>
<pre><code>Tags: /{table}
Consumes: application/json
Produces: */*
</code></pre>
</blockquote>
<h3 id="implementation-notes">Implementation Notes:</h3>
<p>Use to update data for multiple records.</p>
<h3 id="parameters">Parameters:</h3>

<table>
<thead>
<tr>
<th align="left">Type</th>
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Schema</th>
<th align="left">Default</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Path</td>
<td align="left"><strong>Table</strong> (<em>required</em>)</td>
<td align="left">The table to update</td>
<td align="left">String</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">Records</td>
<td align="left">List[Map«string,object»]</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">Principal</td>
<td align="left">Principal</td>
<td align="left"></td>
</tr>
</tbody>
</table><h3 id="swagger-ui-example">Swagger UI Example:</h3>
<pre><code>[{
"cntn_pk" : "200",
"cntn_cf_testSpecificForContentA" : "test2223",
"cntn_mass": {"amount": "12", "unit_pk": "6", "unit_display":"g"},
"cntn_collectionDate":"2017-07-01T11:12:00.000000"
},
{
"cntn_pk" : "201",
"cntn_cf_testSpecificForContentA" : "test"
}]
</code></pre>
<blockquote>
<p>(Date format: yyyy-MM-dd’T’HH:mm:ss.SSSSSS)</p>
</blockquote>
<h3 id="responses">Responses:</h3>
<ul>
<li>200 : Success - Rest Fetch Response</li>
<li>201: Created - No Content</li>
<li>401: Unauthorized - No Content</li>
<li>403: Forbidden - No Content</li>
<li>404: Not Found - No Content</li>
</ul>
<h2 id="fetch-records-by-criteria">Fetch Records by Criteria</h2>
<blockquote>
<p><strong>GET</strong></p>
<pre><code>Tags: /{table}
Consumes: application/json
Produces: */*
</code></pre>
</blockquote>
<h3 id="implementation-notes-1">Implementation Notes:</h3>
<p>Allows users to fetch on a table with certain basic criteria. For example, you can fetch all content by browsing to: <a href="http://slims.customer.com/slimsrest/rest/Content">http://slims.customer.com/slimsrest/rest/Content</a>, and all Content with a certain id by using query parameters: <a href="http://slims.customer.com/slimsrest/rest/Content?cntn_id=SomeId">http://slims.customer.com/slimsrest/rest/Content?cntn_id=SomeId</a>. Usage of query parameters, like in the latter example, is not yet supported to try out in the parameters section of this framework.</p>
<h3 id="parameters-1">Parameters:</h3>

<table>
<thead>
<tr>
<th align="left">Type</th>
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Schema</th>
<th align="left">Default</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Path</td>
<td align="left"><strong>Table</strong> (<em>required</em>)</td>
<td align="left">The table to look up</td>
<td align="left">String</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">Principal</td>
<td align="left">Principal</td>
<td align="left"></td>
</tr>
</tbody>
</table><h3 id="responses-1">Responses:</h3>
<ul>
<li>200 : Success - Rest Fetch Response</li>
<li>401: Unauthorized - No Content</li>
<li>403: Forbidden - No Content</li>
<li>404: Not Found - No Content</li>
</ul>
<h2 id="add-a-record">Add a Record</h2>
<blockquote>
<p><strong>PUT</strong></p>
<pre><code>Tags: /{table}
Consumes: application/json
Produces: */*
</code></pre>
</blockquote>
<h3 id="implementation-notes-2">Implementation Notes:</h3>
<p>Create a new Content.</p>
<h3 id="parameters-2">Parameters:</h3>

<table>
<thead>
<tr>
<th align="left">Type</th>
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Schema</th>
<th align="left">Default</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Path</td>
<td align="left"><strong>Table</strong> (<em>required</em>)</td>
<td align="left">The table to add in</td>
<td align="left">String</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">Record</td>
<td align="left">Object</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">Principal</td>
<td align="left">Principal</td>
<td align="left"></td>
</tr>
</tbody>
</table><h3 id="swagger-ui-example-1">Swagger UI Example:</h3>
<pre><code>{
"cntn_fk_contentType":"11",
"cntn_status":"10",
"cntn_cf_testSpecificForContentA" : "test2223",
"cntn_mass": {"amount": "12", "unit_pk": "6", "unit_display":"g"}
}
</code></pre>
<h3 id="responses-2">Responses:</h3>
<ul>
<li>200 : Success - Rest Fetch Response</li>
<li>201: Created - No Content</li>
<li>401: Unauthorized - No Content</li>
<li>403: Forbidden - No Content</li>
<li>404: Not Found - No Content</li>
</ul>
<h2 id="update-a-record-by-pk">Update a Record by Pk</h2>
<blockquote>
<p><strong>POST</strong></p>
<pre><code>**Tags:** /{table}/{pk}
Consumes: application/json
Produces: */*
</code></pre>
</blockquote>
<h3 id="implementation-notes-3">Implementation Notes:</h3>
<p>Update a single Content.</p>
<h3 id="parameters-3">Parameters:</h3>

<table>
<thead>
<tr>
<th align="left">Type</th>
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Schema</th>
<th align="left">Default</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Path</td>
<td align="left"><strong>Table</strong> (<em>required</em>)</td>
<td align="left">The table to update</td>
<td align="left">String</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Pk</strong> (<em>required</em>)</td>
<td align="left">The primary key of the record to update</td>
<td align="left">Integer(int64)</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">Values</td>
<td align="left">Object</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">Principal</td>
<td align="left">Principal</td>
<td align="left"></td>
</tr>
</tbody>
</table><h3 id="swagger-ui-example-2">Swagger UI Example:</h3>
<pre><code>{
    "cntn_cf_testSpecificForContentA" : "test2223",
   "cntn_mass": {"amount": "12", "unit_pk": "6", "unit_display":"g"}
}
</code></pre>
<h3 id="responses-3">Responses:</h3>
<ul>
<li>200 : Success - Rest Fetch Response</li>
<li>201: Created - No Content</li>
<li>401: Unauthorized - No Content</li>
<li>403: Forbidden - No Content</li>
<li>404: Not Found - No Content</li>
</ul>
<h2 id="remove-a-record-by-pk">Remove a Record by Pk</h2>
<blockquote>
<p><strong>DELETE</strong></p>
<pre><code>**Tags:** /{table}/{pk}
Consumes: application/json
Produces: */*
</code></pre>
</blockquote>
<h3 id="implementation-notes-4">Implementation Notes:</h3>
<p>Delete a single Content.</p>
<h3 id="parameters-4">Parameters:</h3>

<table>
<thead>
<tr>
<th align="left">Type</th>
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Schema</th>
<th align="left">Default</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Path</td>
<td align="left"><strong>Table</strong> (<em>required</em>)</td>
<td align="left">The table remove a record from</td>
<td align="left">String</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Pk</strong> (<em>required</em>)</td>
<td align="left">The primary key of the record to remove</td>
<td align="left">Integer(int64)</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">Principal</td>
<td align="left">Principal</td>
<td align="left"></td>
</tr>
</tbody>
</table><h3 id="swagger-ui-example-3">Swagger UI Example:</h3>
<pre><code>
</code></pre>
<h3 id="responses-4">Responses:</h3>
<ul>
<li>200 : Success - Rest Fetch Response</li>
<li>204: No Content - No Content</li>
<li>401: Unauthorized - No Content</li>
<li>403: Forbidden - No Content</li>
</ul>
<h2 id="fetch-records-by-primary-key">Fetch Records by Primary Key</h2>
<blockquote>
<p><strong>GET</strong></p>
<pre><code>**Tags:** /{table}/{pks}
Consumes: application/json
Produces: */*
</code></pre>
</blockquote>
<h3 id="implementation-notes-5">Implementation Notes:</h3>
<p>Get multiple packages by their primary keys.</p>
<h3 id="parameters-5">Parameters:</h3>

<table>
<thead>
<tr>
<th align="left">Type</th>
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Schema</th>
<th align="left">Default</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Path</td>
<td align="left"><strong>Table</strong> (<em>required</em>)</td>
<td align="left">The table to look up</td>
<td align="left">String</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Pks</strong> (<em>Comma separated list of pks</em>)</td>
<td align="left">The primary key(s) of the record(s) to look up</td>
<td align="left">String</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">Principal</td>
<td align="left">Principal</td>
<td align="left"></td>
</tr>
</tbody>
</table><h3 id="swagger-ui-example-4">Swagger UI Example:</h3>
<pre><code>
</code></pre>
<h3 id="responses-5">Responses:</h3>
<ul>
<li>200 : Success - Rest Fetch Response</li>
<li>401: Unauthorized - No Content</li>
<li>403: Forbidden - No Content</li>
<li>404: Not Found - No Content</li>
</ul>
<h2 id="fetch-records-with-advanced-criteria-sorting-and-paging">Fetch Records with Advanced Criteria, Sorting, and Paging</h2>
<blockquote>
<p><strong>GET</strong></p>
<pre><code>**Tags:** /{table}/advanced
Consumes: application/json
Produces: */*
</code></pre>
</blockquote>
<h3 id="implementation-notes-6">Implementation Notes:</h3>
<p>Allows users to fetch on a table with advanced criteria, server side sorting, and paging. The request body can contain the following criteria. All are optional.</p>
<h3 id="criteria">Criteria:</h3>
<p>Allows server side filtering. For example, you can fetch content for which the ID is equal to “example” like this:</p>
<pre><code>{"fieldName": "cntn_id", "operator": "equals", "value": "example"}
</code></pre>
<p>Searches on all fields are allowed. The operators we currently support are:</p>
<pre><code>equals
notEqual
greaterThan
lessThan
greaterOrEqual
lessOrEqual
contains
startsWith
endsWith
between
betweenInclusive
isNull
isNotNull
</code></pre>
<p>Some examples for this are:</p>
<pre><code>{"fieldName": "cntn_id", "operator": "startsWith", "value": "DNA00"}
</code></pre>
<pre><code>{"fieldName": "cntn_fk_location", "operator": "isNull"}
</code></pre>
<pre><code>{"fieldName": "cntn_createdOn", "operator": "between", "start": "2016-11-20T00:00:00.000000", "end": "2016-11-22T00:00:00.000000"}
</code></pre>
<p>Note the way of passing dates here.<br>
Criteria can be combined or negated using constructs like this:</p>
<pre><code>{"operator":"and","criteria":[the list of criteria to combine]}
</code></pre>
<pre><code>{"operator":"or","criteria":[the list of criteria to combine]}
</code></pre>
<pre><code>{"operator":"not","criteria":[criteria to negate]}
</code></pre>
<h4 id="sorting">Sorting</h4>
<p>Sorts the returned list of records. You can pass a list here and the sorting will be applied after each other. For example:</p>
<pre><code>["cntn_id", "cntn_barCode"]
</code></pre>
<p>The above will sort the returned content first on ID (ascending) and then on barcode (ascending). To sort descending, prepend the field with a hyphen (-). For example:</p>
<pre><code>["-cntn_id"]
</code></pre>
<h4 id="start-and-end-row">Start and End Row</h4>
<p>These two properties only have effect if used together. Allows a user to only query for a subset of the matched records.</p>
<h3 id="complete-request">Complete Request</h3>
<p>A complete request should look like this:</p>
<pre><code>{
"criteria": {"fieldName": "cntn_id", "operator": "equals", "value": "example"},
"sortBy": ["cntn_createdOn"],
"startRow":10,
"endRow":20
}
</code></pre>
<p>…And fetches the 10th to 20th samples with ID example sorted by the creation date.</p>
<h3 id="try-it-out">Try it out!</h3>
<p>Contrary to standard HTTP specifications, this document framework does not support GET requests with a body. But you can try it out using the following curl command:</p>
<pre><code>curl -u user:password -X GET -H 'Content-Type: application/json' \
	-d '{"criteria": {"fieldName": "cntp_name", "operator": "equals", "value": "DNA"}}' \
	http://slims.customer.com/slimsrest/rest/ContentType/advanced
</code></pre>
<h3 id="parameters-6">Parameters:</h3>

<table>
<thead>
<tr>
<th align="left">Type</th>
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Schema</th>
<th align="left">Default</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Path</td>
<td align="left"><strong>Table</strong> (<em>required</em>)</td>
<td align="left">The table to look up</td>
<td align="left">String</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>required</em>)</td>
<td align="left">The request</td>
<td align="left">Model / Model Schema</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">Principal</td>
<td align="left">Principal</td>
<td align="left"></td>
</tr>
</tbody>
</table><h3 id="swagger-ui-example-5">Swagger UI Example:</h3>
<pre><code>
</code></pre>
<h3 id="responses-6">Responses:</h3>
<ul>
<li>200 : Success - Rest Fetch Response</li>
<li>401: Unauthorized - No Content</li>
<li>403: Forbidden - No Content</li>
<li>404: Not Found - No Content</li>
</ul>
<h1 id="a-idtoc4content-linked-in-elna"><a id="toc4"></a><a href="#toc">CONTENT LINKED IN ELN</a></h1>
<h2 id="fetch-content-linked-to-an-experiment-run-step">Fetch Content Linked to an Experiment Run Step</h2>
<blockquote>
<p><strong>GET</strong></p>
<pre><code>**Tags:** /eln/content/{usage}/{experimentRunStepPk}
Consumes: application/json
Produces: */*
</code></pre>
</blockquote>
<h3 id="implementation-notes-7">Implementation Notes:</h3>
<p>Fetch the content that is linked to an experiment run step.</p>
<h3 id="parameters-7">Parameters:</h3>

<table>
<thead>
<tr>
<th align="left">Type</th>
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Schema</th>
<th align="left">Default</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Path</td>
<td align="left"><strong>Usage</strong> (<em>required</em>)</td>
<td align="left">Input or output</td>
<td align="left">String</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Path</td>
<td align="left"><strong>experimentRunStepPk</strong> (<em>required</em>)</td>
<td align="left">The primary key of the experiment run step</td>
<td align="left">Integer(int64)</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">Principal</td>
<td align="left">Principal</td>
<td align="left"></td>
</tr>
</tbody>
</table><h3 id="swagger-ui-example-6">Swagger UI Example:</h3>
<pre><code>
</code></pre>
<h3 id="responses-7">Responses:</h3>
<ul>
<li>200 : Success - Rest Fetch Response</li>
<li>401: Unauthorized - No Content</li>
<li>403: Forbidden - No Content</li>
<li>404: Not Found - No Content</li>
</ul>
<h2 id="unlink-content-from-an-experiment-run-step">Unlink Content from an Experiment Run Step</h2>
<blockquote>
<p><strong>DELETE</strong></p>
<pre><code>**Tags:** /eln/content/{usage}/{experimentRunStepPk}/{contentPk}
Consumes: application/json
Produces: */*
</code></pre>
</blockquote>
<h3 id="implementation-notes-8">Implementation Notes:</h3>
<p>Unlink a content from an experiment run step.</p>
<h3 id="parameters-8">Parameters:</h3>

<table>
<thead>
<tr>
<th align="left">Type</th>
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Schema</th>
<th align="left">Default</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Path</td>
<td align="left"><strong>Usage</strong> (<em>required</em>)</td>
<td align="left">Input or output</td>
<td align="left">String</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Path</td>
<td align="left"><strong>experimentRunStepPk</strong> (<em>required</em>)</td>
<td align="left">The primary key of the experiment run step</td>
<td align="left">Integer(int64)</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Path</td>
<td align="left"><strong>contentPk</strong> (<em>required</em>)</td>
<td align="left">The primary key of the content</td>
<td align="left">Integer(int64)</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">Principal</td>
<td align="left">Principal</td>
<td align="left"></td>
</tr>
</tbody>
</table><h3 id="swagger-ui-example-7">Swagger UI Example:</h3>
<pre><code>
</code></pre>
<h3 id="responses-8">Responses:</h3>
<ul>
<li>200 : Success - Rest Fetch Response</li>
<li>204: No Content - No Content</li>
<li>401: Unauthorized - No Content</li>
<li>403: Forbidden - No Content</li>
</ul>
<h2 id="link-content-to-an-experiment-run-step">Link Content to an Experiment Run Step</h2>
<blockquote>
<p><strong>POST</strong></p>
<pre><code>Tags: /eln/content/{usage}/{experimentRunStepPk}/{contentPk}
Consumes: application/json
Produces: */*
</code></pre>
</blockquote>
<h3 id="implementation-notes-9">Implementation Notes:</h3>
<p>Use to link a content to an Experiment Run Step.</p>
<h3 id="parameters-9">Parameters:</h3>

<table>
<thead>
<tr>
<th align="left">Type</th>
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Schema</th>
<th align="left">Default</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Path</td>
<td align="left"><strong>Usage</strong> (<em>required</em>)</td>
<td align="left">Input or output</td>
<td align="left">String</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Path</td>
<td align="left"><strong>experimentRunStepPk</strong> (<em>required</em>)</td>
<td align="left">The primary key of the experiment run step</td>
<td align="left">Integer (int64)</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Path</td>
<td align="left"><strong>usage</strong> (<em>required</em>)</td>
<td align="left">The primary key of the content</td>
<td align="left">Integer (int64)</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>body</strong> (<em>optional</em>)</td>
<td align="left">Principal</td>
<td align="left">Principal</td>
<td align="left"></td>
</tr>
</tbody>
</table><h3 id="responses-9">Responses:</h3>
<ul>
<li>200 : Success - Rest Fetch Response</li>
<li>201: Created - No Content</li>
<li>401: Unauthorized - No Content</li>
<li>403: Forbidden - No Content</li>
<li>404: Not Found - No Content</li>
</ul>
<h1 id="a-idtoc5content-mix-operationa"><a id="toc5"></a><a href="#toc">CONTENT MIX OPERATION</a></h1>
<h2 id="create-a-mix-of-ingredients">Create a Mix of Ingredients</h2>
<blockquote>
<p><strong>PUT</strong></p>
<pre><code>**Tags:** /actions/content/mix
Consumes: application/json
Produces: */*
</code></pre>
</blockquote>
<h3 id="implementation-notes-10">Implementation Notes:</h3>
<p>Create a mix of selected ingredients.</p>
<h3 id="parameters-10">Parameters:</h3>

<table>
<thead>
<tr>
<th align="left">Type</th>
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Schema</th>
<th align="left">Default</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>required</em>)</td>
<td align="left">Mix values and ingredient pks</td>
<td align="left">Model / Model Schema</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">Principal</td>
<td align="left">Principal</td>
<td align="left"></td>
</tr>
</tbody>
</table><h3 id="swagger-ui-example-8">Swagger UI Example:</h3>
<pre><code>
</code></pre>
<h3 id="responses-10">Responses:</h3>
<ul>
<li>200 : Success - Rest Fetch Response</li>
<li>201: Created - No Content</li>
<li>401: Unauthorized - No Content</li>
<li>403: Forbidden - No Content</li>
<li>404: Not Found - No Content</li>
</ul>
<h1 id="a-idtoc6electronic-lab-notebook-elna"><a id="toc6"></a><a href="#toc">Electronic Lab Notebook (ELN)</a></h1>
<h2 id="fetch-root-of-eln-tree">Fetch Root of ELN Tree</h2>
<blockquote>
<p><strong>GET</strong></p>
<pre><code>**Tags:** /eln
Consumes: application/json
Produces: */*
</code></pre>
</blockquote>
<h3 id="implementation-notes-11">Implementation Notes:</h3>
<p>Fetch the root of the Electronic Lab Notebook tree.</p>
<h3 id="parameters-11">Parameters:</h3>

<table>
<thead>
<tr>
<th align="left">Type</th>
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Schema</th>
<th align="left">Default</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">Principal</td>
<td align="left">Principal</td>
<td align="left"></td>
</tr>
</tbody>
</table><h3 id="swagger-ui-example-9">Swagger UI Example:</h3>
<pre><code>
</code></pre>
<h3 id="responses-11">Responses:</h3>
<ul>
<li>200 : Success - Rest Fetch Response</li>
<li>401: Unauthorized - No Content</li>
<li>403: Forbidden - No Content</li>
<li>404: Not Found - No Content</li>
</ul>
<h2 id="fetch-children-of-a-record-in-eln-tree">Fetch Children of a Record in ELN Tree</h2>
<blockquote>
<p><strong>GET</strong></p>
<pre><code>**Tags:** /eln/{table}/{pk}
Consumes: application/json
Produces: */*
</code></pre>
</blockquote>
<h3 id="implementation-notes-12">Implementation Notes:</h3>
<p>Fetch the children of a record in the Electronic Lab Notebook tree.</p>
<h3 id="parameters-12">Parameters:</h3>

<table>
<thead>
<tr>
<th align="left">Type</th>
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Schema</th>
<th align="left">Default</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Path</td>
<td align="left"><strong>Table</strong> (<em>required</em>)</td>
<td align="left">The table of the parent record</td>
<td align="left">String</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Pk</strong> (<em>required</em>)</td>
<td align="left">The primary key of the parent record</td>
<td align="left">Integer (int64)</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">Principal</td>
<td align="left">Principal</td>
<td align="left"></td>
</tr>
</tbody>
</table><h3 id="swagger-ui-example-10">Swagger UI Example:</h3>
<pre><code>
</code></pre>
<h3 id="responses-12">Responses:</h3>
<ul>
<li>200 : Success - Rest Fetch Response</li>
<li>401: Unauthorized - No Content</li>
<li>403: Forbidden - No Content</li>
<li>404: Not Found - No Content</li>
</ul>
<h2 id="add-a-simplified-block-to-an-experiment-run">Add a Simplified Block to an Experiment Run</h2>
<blockquote>
<p><strong>POST</strong></p>
<pre><code>**Tags:** /eln/ExperimentRun/{pk}
Consumes: application/json
Produces: */*
</code></pre>
</blockquote>
<h3 id="implementation-notes-13">Implementation Notes:</h3>
<p>Add a simplified block to an experiment run.</p>
<h3 id="parameters-13">Parameters:</h3>

<table>
<thead>
<tr>
<th align="left">Type</th>
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Schema</th>
<th align="left">Default</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Pk</strong> (<em>required</em>)</td>
<td align="left">The primary key of the experiment run</td>
<td align="left">Integer (int64)</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">The simplified block parameters (xprs_name, xpst_type should be given)</td>
<td align="left">Object</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">Principal</td>
<td align="left">Principal</td>
<td align="left"></td>
</tr>
</tbody>
</table><h3 id="swagger-ui-example-11">Swagger UI Example:</h3>
<pre><code>
</code></pre>
<h3 id="responses-13">Responses:</h3>
<ul>
<li>200 : Success - Rest Fetch Response</li>
<li>201: Created - No Content</li>
<li>401: Unauthorized - No Content</li>
<li>403: Forbidden - No Content</li>
<li>404: Not Found - No Content</li>
</ul>
<h1 id="a-idtoc7external-service-controllera"><a id="toc7"></a><a href="#toc">External Service Controller</a></h1>
<h2 id="register">Register</h2>
<blockquote>
<p><strong>POST</strong></p>
<pre><code>**Tags:** /{table}/{pk}
Consumes: application/json
Produces: */*
</code></pre>
</blockquote>
<h3 id="implementation-notes-14">Implementation Notes:</h3>
<p>Register.</p>
<h3 id="parameters-14">Parameters:</h3>

<table>
<thead>
<tr>
<th align="left">Type</th>
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Schema</th>
<th align="left">Default</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">addFlowRequest</td>
<td align="left">Model / Model Schema</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">Principal</td>
<td align="left">Principal</td>
<td align="left"></td>
</tr>
</tbody>
</table><h3 id="swagger-ui-example-12">Swagger UI Example:</h3>
<pre><code>
</code></pre>
<h3 id="responses-14">Responses:</h3>
<ul>
<li>200 : Success - Rest Fetch Response</li>
<li>201: Created - No Content</li>
<li>401: Unauthorized - No Content</li>
<li>403: Forbidden - No Content</li>
<li>404: Not Found - No Content</li>
</ul>
<h2 id="log">Log</h2>
<blockquote>
<p><strong>POST</strong></p>
<pre><code>**Tags:** /external/log
Consumes: application/json
Produces: */*
</code></pre>
</blockquote>
<h3 id="implementation-notes-15">Implementation Notes:</h3>
<p>Log.</p>
<h3 id="parameters-15">Parameters:</h3>

<table>
<thead>
<tr>
<th align="left">Type</th>
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Schema</th>
<th align="left">Default</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">flowRunLogMessage</td>
<td align="left">Model / Model Schema</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">Principal</td>
<td align="left">Principal</td>
<td align="left"></td>
</tr>
</tbody>
</table><h3 id="swagger-ui-example-13">Swagger UI Example:</h3>
<pre><code>
</code></pre>
<h3 id="responses-15">Responses:</h3>
<ul>
<li>200 : Success - Rest Fetch Response</li>
<li>201: Created - No Content</li>
<li>401: Unauthorized - No Content</li>
<li>403: Forbidden - No Content</li>
<li>404: Not Found - No Content</li>
</ul>
<h2 id="status">Status</h2>
<blockquote>
<p><strong>POST</strong></p>
<pre><code>**Tags:** /external/status
Consumes: application/json
Produces: */*
</code></pre>
</blockquote>
<h3 id="implementation-notes-16">Implementation Notes:</h3>
<p>Status.</p>
<h3 id="parameters-16">Parameters:</h3>

<table>
<thead>
<tr>
<th align="left">Type</th>
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Schema</th>
<th align="left">Default</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">statusUpdate</td>
<td align="left">Model / Model Schema</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">Principal</td>
<td align="left">Principal</td>
<td align="left"></td>
</tr>
</tbody>
</table><h3 id="swagger-ui-example-14">Swagger UI Example:</h3>
<pre><code>
</code></pre>
<h3 id="responses-16">Responses:</h3>
<ul>
<li>200 : Success - Rest Fetch Response</li>
<li>201: Created - No Content</li>
<li>401: Unauthorized - No Content</li>
<li>403: Forbidden - No Content</li>
<li>404: Not Found - No Content</li>
</ul>
<h2 id="user-secret-check">User Secret Check</h2>
<blockquote>
<p><strong>POST</strong></p>
<pre><code>**Tags:** /external/userSecretCheck
Consumes: application/json
Produces: */*
</code></pre>
</blockquote>
<h3 id="implementation-notes-17">Implementation Notes:</h3>
<p>User secret check.</p>
<h3 id="parameters-17">Parameters:</h3>

<table>
<thead>
<tr>
<th align="left">Type</th>
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Schema</th>
<th align="left">Default</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">userSecretBody</td>
<td align="left">Model / Model Schema</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">Principal</td>
<td align="left">Principal</td>
<td align="left"></td>
</tr>
</tbody>
</table><h3 id="swagger-ui-example-15">Swagger UI Example:</h3>
<pre><code>
</code></pre>
<h3 id="responses-17">Responses:</h3>
<ul>
<li>200 : Success - Rest Fetch Response</li>
<li>201: Created - No Content</li>
<li>401: Unauthorized - No Content</li>
<li>403: Forbidden - No Content</li>
<li>404: Not Found - No Content</li>
</ul>
<h1 id="a-idtoc8file-repository-operationsa"><a id="toc8"></a><a href="#toc">File Repository Operations</a></h1>
<h2 id="upload-a-new-attachment">Upload a New Attachment</h2>
<blockquote>
<p><strong>POST</strong></p>
<pre><code>**Tags:** /repo
Consumes: application/json
Produces: */*
</code></pre>
</blockquote>
<h3 id="implementation-notes-18">Implementation Notes:</h3>
<p>Add an Attachment.</p>
<h3 id="parameters-18">Parameters:</h3>

<table>
<thead>
<tr>
<th align="left">Type</th>
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Schema</th>
<th align="left">Default</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">attachmentValues</td>
<td align="left">Model / Model Schema</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">Principal</td>
<td align="left">Principal</td>
<td align="left"></td>
</tr>
<tr>
<td align="left"></td>
<td align="left"><strong>atln_recordPk</strong> (<em>optional</em>)</td>
<td align="left">The primary key of the record to attach to</td>
<td align="left">Integer (int64)</td>
<td align="left"></td>
</tr>
<tr>
<td align="left"></td>
<td align="left"><strong>atln_recordTable</strong> (<em>optional</em>)</td>
<td align="left">The primary key of the table of the record to attach to</td>
<td align="left">String</td>
<td align="left"></td>
</tr>
</tbody>
</table><h3 id="swagger-ui-example-16">Swagger UI Example:</h3>
<pre><code>
</code></pre>
<h3 id="responses-18">Responses:</h3>
<ul>
<li>200 : Success - Rest Fetch Response</li>
<li>201: Created - No Content</li>
<li>401: Unauthorized - No Content</li>
<li>403: Forbidden - No Content</li>
<li>404: Not Found - No Content</li>
</ul>
<h2 id="download-the-attachment">Download the Attachment</h2>
<blockquote>
<p><strong>GET</strong></p>
<pre><code>**Tags:** /repo/{pk}
Consumes: application/json
Produces: */*
</code></pre>
</blockquote>
<h3 id="implementation-notes-19">Implementation Notes:</h3>
<p>Download the attachment from the package.</p>
<h3 id="parameters-19">Parameters:</h3>

<table>
<thead>
<tr>
<th align="left">Type</th>
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Schema</th>
<th align="left">Default</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Path</td>
<td align="left"><strong>Pk</strong> (<em>required</em>)</td>
<td align="left">pk</td>
<td align="left">Integer (int64)</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">Principal</td>
<td align="left">Principal</td>
<td align="left"></td>
</tr>
</tbody>
</table><h3 id="swagger-ui-example-17">Swagger UI Example:</h3>
<pre><code>
</code></pre>
<h3 id="responses-19">Responses:</h3>
<ul>
<li>200 : Success - Rest Fetch Response</li>
<li>401: Unauthorized - No Content</li>
<li>403: Forbidden - No Content</li>
<li>404: Not Found - No Content</li>
</ul>
<h1 id="a-idtoc9queuea"><a id="toc9"></a><a href="#toc">Queue</a></h1>
<h2 id="fetch-record-in-queue-in-a-certain-status">Fetch Record in Queue in a Certain Status</h2>
<blockquote>
<p><strong>GET</strong></p>
<pre><code>**Tags:** /queue/content/{queue}/{status}
Consumes: application/json
Produces: */*
</code></pre>
</blockquote>
<h3 id="implementation-notes-20">Implementation Notes:</h3>
<p>Allows users to fetch the samples in a queue that are in a certain status. The possible statuses are: NOT_STARTED, IN_PROGRESS, APPROVAL, DONE, and CANCELLED. For example, you can fetch all content on the “Start” queue that are not in an experiment yet by querying /queue/content/Start/NOT_STARTED</p>
<h3 id="parameters-20">Parameters:</h3>

<table>
<thead>
<tr>
<th align="left">Type</th>
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Schema</th>
<th align="left">Default</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Path</td>
<td align="left"><strong>Queue</strong> (<em>required</em>)</td>
<td align="left">The queue to look in</td>
<td align="left">String</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Path</td>
<td align="left"><strong>Status</strong> (<em>required</em>)</td>
<td align="left">The status of the elements in the queue</td>
<td align="left">String</td>
<td align="left"></td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>Body</strong> (<em>optional</em>)</td>
<td align="left">Principal</td>
<td align="left">Principal</td>
<td align="left"></td>
</tr>
</tbody>
</table><h3 id="swagger-ui-example-18">Swagger UI Example:</h3>
<pre><code>
</code></pre>
<h3 id="responses-20">Responses:</h3>
<ul>
<li>200 : Success - Rest Fetch Response</li>
<li>401: Unauthorized - No Content</li>
<li>403: Forbidden - No Content</li>
<li>404: Not Found - No Content</li>
</ul>
<blockquote>
<p>Copyright © Genohm 2018, All Rights Reserved<br>
Written with <a href="https://stackedit.io/">StackEdit</a>.</p>
</blockquote>

    </div>
  </div>
</body>

</html>
