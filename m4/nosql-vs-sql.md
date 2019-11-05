---
title: Module 4 - NoSQL vs SQL
---

# Module 4: NoSQL Document Based DB 🤜💥🤛 SQL Relational DB

<table>
    <tbody>
        <tr>
            <td></td>
            <td><h2>SQL</h2></td>
            <td><h2>NoSQL</h2</td>
            <td></td>
        </tr>
        <tr>
            <td><h3>storage</h3</td>
            <td><strong>tables</strong></td>
            <td><strong>collections</strong></td>
        </tr>
        <tr>
            <td><h3>object encapsulation</h3></td>
            <td>
                <strong>rows</strong><br/>
                <small>
                    👉 object may be split into multiple rows and across multiple tables (requiring ORM)<br/>
                    👉 normalized to remove duplication<br/>
                    👉 a single row may or may not have meaning to the application<br/>
                    👉 query with joins<br/>
                    👉 ORM to help read / write objects across tables
                </small>
            </td>
            <td>
                <strong>documents</strong><br/>
                <small>
                    👉 "semi-structured data"<br/>
                    👉 an entire object is typically encoded into a single document<br/>
                    👉 <strong>de-normalized</strong> to improve query perf & API requests (makes updates and deletions complex 👎😿)
                </small>
            </td>
        </tr>
        <tr>
            <td><h3>identification</h3></td>
            <td>
                <strong>primary key</strong><br/>
                <small>👉1 row may not be an entire object</small>
            </td>
            <td>
                <strong>document id</strong><br/>
                <small>
                    👉 key value pair<br/>
                    👉 entire document can be fetched with id
                </small>
            </td>
        </tr>
        <tr>
            <td><h3>organization</h3></td>
            <td><strong>table names</strong></td>
            <td>
                <strong>tree</strong><br/>
                <small>👉 similar to filesystem (directories and files)</small>
            </td>
        </tr>
        <tr>
            <td><h3>encoding</h3></td>
            <td>
                <strong>table schema</strong><br/>
                <small>👉 column types</small>
            </td>
            <td>
                encoded into <strong>standard format</strong><br/>
                <small>👉 JSON, XML, etc.</small>
            </td>
        </tr>
        <tr>
            <td><h3>indexes</h3></td>
            <td>yes</td>
            <td>yes</td>
        </tr>
        <tr>
            <td><h3>queries</h3></td>
            <td>
                <strong>SQL</strong> query language<br/>
                <small>👉 powerful and complicated</small>
            </td>
            <td>Query <strong>API</strong> or language<br/>
                <small>👉 generally simpler but limited</small>
            </td>
        </tr>
        <tr>
            <td><h3>schema</h3></td>
            <td>
                defined at table creation <em>before</em> adding data<br/>
                <small>👉 can be modified, but every row must match schema</small>
            </td>
            <td>
                <strong>no schema</strong><br/>
                <small>👉 documents still <em>need</em> common structure to facilitate queries, but this is not enforced by the DB</small>
            </td>
        </tr>
        <tr>
            <td><h3>schema migrations</h3></td>
            <td>
                <strong>data must always be valid</strong><br/>
                <small>
                    👉 add new columns then complete existing rows<br/>
                    👉 often done with service "offline"
                </small>
            </td>
            <td>
                <strong>data is never validated</strong><br/>
                <small>
                    👉 modify all existing data to new structure (may require going "offline")<br/>
                    👉 migrate data at application time documents are accessed (requires code that supports multiple versions of structure)
                </small>
            </td>
        </tr>
        <tr>
            <td><h3>scalability</h3></td>
            <td>
                <strong>vertical</strong><br/>
                <small>
                    👉 add memory, CPU, SSD, etc.<br/>
                    👉 adding floors to a building
                </small>
            </td>
            <td>
                <strong>horizontal</strong><br/>
                <small>
                    👉 sharding (replication over multiple servers/sites)<br/>
                    👉 adding buildings to a neighborhood
                </small>
            </td>
        </tr>
        <tr>
            <td><h3>examples</h3></td>
            <td>PostgreSQL, MySQL, Oracle, Microsoft SQL server</td>
            <td>MongoDB, Redis, Cassandra, CouchDB, Firestore</td>
        </tr>
    </tbody>
</table>
