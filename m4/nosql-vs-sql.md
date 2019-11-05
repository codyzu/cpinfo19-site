---
title: Module 4 - NoSQL vs SQL
---

# Module 4: NoSQL Document Based DB vs SQL Relational DB

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
            <td>documents</td>
        </tr>
        <tr>
            <td><h3>identification</h3></td>
            <td>primary key in table</td>
            <td>document id (key value pair)</td>
        </tr>
        <tr>
            <td><h3>organization</h3></td>
            <td>table names, namespaces</td>
            <td>tree, similar to filesystem</td>
        </tr>
        <tr>
            <td><h3>encoding</h3></td>
            <td>column types</td>
            <td>encoded into standard format: JSON, XML, etc.</td>
        </tr>
        <tr>
            <td><h3>indexes</h3></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td><h3>queries</h3></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td><h3>objects</h3></td>
            <td>normalized into multiple tables</td>
            <td>
                objects stored in their entirety<br/>
                de-normalized to improve query perf
            </td>
        </tr>
        <tr>
            <td><h3>schema</h3></td>
            <td>must be defined at table creation, can be modified, but every row mush match schema</td>
            <td>no schema</td>
        </tr>
    </tbody>
</table>

