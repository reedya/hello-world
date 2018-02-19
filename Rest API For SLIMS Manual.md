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
<li></li>
</ul>
</li>
<li><a href="#a-idtoc6electronic-lab-notebook-elna">Electronic Lab Notebook (ELN)</a>
<ul>
<li></li>
</ul>
</li>
<li><a href="#a-idtoc7external-service-controllera">External Service Controller</a>
<ul>
<li></li>
</ul>
</li>
<li><a href="#a-idtoc8file-repository-operationsa">File Repository Operations</a>
<ul>
<li></li>
</ul>
</li>
<li><a href="#a-idtoc9queuea">Queue</a>
<ul>
<li></li>
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
<h3 id="displayableentitycolumn«object»">DisplayableEntityColumn«object»</h3>

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
</table><h3 id="displayableentityresource">DisplayableEntityResource</h3>

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
<td align="left"><a href="###DisplayableEntityColumn%C2%ABobject%C2%BB">&lt; DisplayableEntityColumn«object» &gt;</a> array</td>
</tr>
<tr>
<td align="left">links (<em>optional</em>)</td>
<td align="left"><a href="###Link">&lt; Link &gt;</a> array</td>
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
<td align="left"><a href="###DisplayableEntityResource">&lt; DisplayableEntityResource &gt;</a> array</td>
</tr>
</tbody>
</table><h1 id="a-idtoc3basic-table-operationsa"><a id="toc3"></a><a href="#toc">BASIC TABLE OPERATIONS</a></h1>
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
</table><h3 id="responses">Responses:</h3>
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
<p>Add a single record.</p>
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
</table><h3 id="responses-2">Responses:</h3>
<ul>
<li>200 : Success - Rest Fetch Response</li>
<li>201: Created - No Content</li>
<li>401: Unauthorized - No Content</li>
<li>403: Forbidden - No Content</li>
<li>404: Not Found - No Content</li>
</ul>
<h2 id="update-a-record-by-pk">Update a Record by Pk</h2>
<h2 id="remove-a-record-by-pk">Remove a Record by Pk</h2>
<h2 id="fetch-records-by-primary-key">Fetch Records by Primary Key</h2>
<h2 id="fetch-records-with-advanced-criteria-sorting-and-paging">Fetch Records with Advanced Criteria, Sorting, and Paging</h2>
<h1 id="a-idtoc4content-linked-in-elna"><a id="toc4"></a><a href="#toc">CONTENT LINKED IN ELN</a></h1>
<h2 id="fetch-content-linked-to-an-experiment-run-step">Fetch Content Linked to an Experiment Run Step</h2>
<h2 id="unlink-content-from-an-experiment-run-step">Unlink Content from an Experiment Run Step</h2>
<h2 id="link-content-to-an-experiment-run-step">Link Content to an Experiment Run Step</h2>
<blockquote>
<p><strong>POST</strong></p>
<pre><code>Tags: /eln/content/{usage}/{experimentRunStepPk}/{contentPk}
Consumes: application/json
Produces: */*
</code></pre>
</blockquote>
<h3 id="implementation-notes-3">Implementation Notes:</h3>
<p>Use to link content to an Experiment Run Step.</p>
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
<td align="left"><strong>contentPk</strong> (<em>required</em>)</td>
<td align="left">The primary key of the content</td>
<td align="left">Integer (int64)</td>
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
<td align="left">Input or output</td>
<td align="left">String</td>
<td align="left">“”</td>
</tr>
<tr>
<td align="left">Body</td>
<td align="left"><strong>body</strong> (<em>optional</em>)</td>
<td align="left">Principal</td>
<td align="left">Principal</td>
<td align="left"></td>
</tr>
</tbody>
</table><h3 id="responses-3">Responses:</h3>
<ul>
<li>200 : Success - Rest Fetch Response</li>
<li>201: Created - No Content</li>
<li>401: Unauthorized - No Content</li>
<li>403: Forbidden - No Content</li>
<li>404: Not Found - No Content</li>
</ul>
<h1 id="a-idtoc5content-mix-operationa"><a id="toc5"></a><a href="#toc">CONTENT MIX OPERATION</a></h1>
<h3 id="create-a-mix-of-ingredients">CREATE A MIX OF INGREDIENTS</h3>
<h1 id="a-idtoc6electronic-lab-notebook-elna"><a id="toc6"></a><a href="#toc">Electronic Lab Notebook (ELN)</a></h1>
<h3 id="fetch-root-of-eln-tree">FETCH ROOT OF ELN TREE</h3>
<h3 id="fetch-children-of-a-record-in-eln-tree">FETCH CHILDREN OF A RECORD IN ELN TREE</h3>
<h3 id="add-a-simplified-block-to-an-experiment-run">ADD A SIMPLIFIED BLOCK TO AN EXPERIMENT RUN</h3>
<h1 id="a-idtoc7external-service-controllera"><a id="toc7"></a><a href="#toc">External Service Controller</a></h1>
<h3 id="register">REGISTER</h3>
<h3 id="log">LOG</h3>
<h3 id="status">STATUS</h3>
<h3 id="user-secret-check">USER SECRET CHECK</h3>
<h1 id="a-idtoc8file-repository-operationsa"><a id="toc8"></a><a href="#toc">File Repository Operations</a></h1>
<h3 id="upload-a-new-attachment">UPLOAD A NEW ATTACHMENT</h3>
<h3 id="download-the-attachment">DOWNLOAD THE ATTACHMENT</h3>
<h1 id="a-idtoc9queuea"><a id="toc9"></a><a href="#toc">Queue</a></h1>
<h3 id="fetch-record-in-a-queue-in-a-certain-status">FETCH RECORD IN A QUEUE IN A CERTAIN STATUS</h3>
<blockquote>
<p>Copyright © Genohm 2018, All Rights Reserved<br>
Written with <a href="https://stackedit.io/">StackEdit</a>.</p>
</blockquote>

    </div>
  </div>
</body>

</html>
