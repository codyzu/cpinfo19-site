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
            <td><strong>tables</strong</td>
            <td><strong>collections</strong></td>
        </tr>
        <tr>
            <td><h3>encapsulation</h3></td>
            <td>
                <strong>rows</strong><br/>
                <small>👉 object may be split into multiple rows and across multiple tables</small>
            </td>
            <td><strong>documents</strong></td>
        </tr>
        <tr>
            <td><h3>identification</h3></td>
            <td><strong>primary key</strong></td>
            <td>
                <strong>document id</strong><br/>
                <small>👉 key value pair</small>
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
            <td><strong>SQL</strong> query language</td>
            <td><strong>Query API</strong></td>
        </tr>
        <tr>
            <td><h3>objects</h3></td>
            <td><strong>normalized</strong> into multiple tables & rows</td>
            <td>
                objects stored in their entirety<br/>
                <small>👉 <strong>de-normalized</strong> to improve query perf & API requests</small>
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
    </tbody>
</table>

