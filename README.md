# Social Network SQL Project
Megadados - Insper

Arthur Olga,
Juan Garcia

## Creating the Database
Run ```make_birdbook.sql```, ```delta_birdbook.sql``` and ```make_triggers.sql```

### Entity-Relationshop Model
<img src="EntityRelationModel.png" >

### Schema Model
<img width="700px" src="Model.png" >

### API
To run the API server:
```
hypercorn server:app --reload
```
### Dictionary

<html><head>
<title>Schema Report for database: birdbook</title>
<style>
        td,th {
        text-align:left;
        vertical-align:middle;
        }
        table {
        border-collapse: collapse;
        border: 1px solid;
        }
        caption, th, td {
        padding: .2em .8em;
        border: 1px solid #000000;
        }
        caption {
        background: #D3D3D3;
        font-weight: bold;
        font-size: 1.1em;
        }
        th {
        font-weight: bold;
        background: #000000;
        color: white;
        }
        td {
        background: #FFFFFF;
        }
        </style>
      </head>
     <body>
<h1>Schema Report for database: birdbook</h1>
<a id="home">Table List </a><br /><ul>
<li><a href="#bird">bird </a></li>
<li><a href="#person">person </a></li>
<li><a href="#person_comment_post">person_comment_post </a></li>
<li><a href="#person_favorites_bird">person_favorites_bird </a></li>
<li><a href="#person_view_post">person_view_post </a></li>
<li><a href="#person_vote_post">person_vote_post </a></li>
<li><a href="#post">post </a></li>
<li><a href="#post_refere_bird">post_refere_bird </a></li>
<li><a href="#post_refere_person">post_refere_person </a></li>
</ul>
<a id="bird"></a><table style="width:100%"><caption>Table: bird </caption>
<tr><td>Table Comments</td><td colspan="6"></td></tr>
<tr><td colspan="7">Columns</td></tr>
        <tr>
        <th>Name</th>
        <th>Data Type</th>
        <th>NOT NULL</th>
        <th>PK</th>
        <th>FK</th>
        <th>Default</th>
        <th>UNIQUE</th>
        <th>Comment</th>
        </tr>
<tr><td>bird_name</td><td>VARCHAR(45)</td><td>Yes</td><td>Yes</td><td>No</td><td></td><td></td><td>Nome do passaro</td></tr>
</table><a href="#home">Table List </a></br>
<a id="person"></a><table style="width:100%"><caption>Table: person </caption>
<tr><td>Table Comments</td><td colspan="6"></td></tr>
<tr><td colspan="7">Columns</td></tr>
        <tr>
        <th>Name</th>
        <th>Data Type</th>
        <th>NOT NULL</th>
        <th>PK</th>
        <th>FK</th>
        <th>Default</th>
        <th>UNIQUE</th>
        <th>Comment</th>
        </tr>
<tr><td>person_id</td><td>SMALLINT(5)</td><td>Yes</td><td>Yes</td><td>No</td><td></td><td></td><td></td></tr>
<tr><td>username</td><td>VARCHAR(45)</td><td>Yes</td><td>No</td><td>No</td><td></td><td>Yes</td><td></td></tr>
<tr><td>first_name</td><td>VARCHAR(45)</td><td>Yes</td><td>No</td><td>No</td><td></td><td></td><td></td></tr>
<tr><td>last_name</td><td>VARCHAR(45)</td><td>Yes</td><td>No</td><td>No</td><td></td><td></td><td></td></tr>
<tr><td>email</td><td>VARCHAR(255)</td><td>Yes</td><td>No</td><td>No</td><td></td><td></td><td></td></tr>
<tr><td>city</td><td>VARCHAR(45)</td><td>Yes</td><td>No</td><td>No</td><td></td><td></td><td></td></tr>
<tr><td>is_deleted</td><td>TINYINT(4)</td><td>Yes</td><td>No</td><td>No</td><td>'0'</td><td></td><td>Variavel para soft delete</td></tr>
</table><a href="#home">Table List </a></br>
<a id="person_comment_post"></a><table style="width:100%"><caption>Table: person_comment_post </caption>
<tr><td>Table Comments</td><td colspan="6"></td></tr>
<tr><td colspan="7">Columns</td></tr>
        <tr>
        <th>Name</th>
        <th>Data Type</th>
        <th>NOT NULL</th>
        <th>PK</th>
        <th>FK</th>
        <th>Default</th>
        <th>UNIQUE</th>
        <th>Comment</th>
        </tr>
<tr><td>comment_id</td><td>SMALLINT(5)</td><td>Yes</td><td>Yes</td><td>No</td><td></td><td></td><td></td></tr>
<tr><td>person_id</td><td>SMALLINT(5)</td><td>Yes</td><td>No</td><td>Yes</td><td></td><td></td><td>Id da pessoa q comentou</td></tr>
<tr><td>post_id</td><td>SMALLINT(5)</td><td>Yes</td><td>No</td><td>Yes</td><td></td><td></td><td></td></tr>
<tr><td>comment</td><td>VARCHAR(255)</td><td>Yes</td><td>No</td><td>No</td><td></td><td></td><td>Conteudo do comentario</td></tr>
<tr><td>deletedAt</td><td>DATETIME</td><td>No</td><td>No</td><td>No</td><td>NULL</td><td></td><td>Variavel de datetime para soft delete</td></tr>
</table><a href="#home">Table List </a></br>
<a id="person_favorites_bird"></a><table style="width:100%"><caption>Table: person_favorites_bird </caption>
<tr><td>Table Comments</td><td colspan="6"></td></tr>
<tr><td colspan="7">Columns</td></tr>
        <tr>
        <th>Name</th>
        <th>Data Type</th>
        <th>NOT NULL</th>
        <th>PK</th>
        <th>FK</th>
        <th>Default</th>
        <th>UNIQUE</th>
        <th>Comment</th>
        </tr>
<tr><td>person_id</td><td>SMALLINT(5)</td><td>Yes</td><td>Yes</td><td>Yes</td><td></td><td></td><td></td></tr>
<tr><td>bird_name</td><td>VARCHAR(45)</td><td>Yes</td><td>Yes</td><td>Yes</td><td></td><td></td><td></td></tr>
<tr><td>deletedAt</td><td>DATETIME</td><td>No</td><td>No</td><td>No</td><td>NULL</td><td></td><td>Variavel de soft delete</td></tr>
</table><a href="#home">Table List </a></br>
<a id="person_view_post"></a><table style="width:100%"><caption>Table: person_view_post </caption>
<tr><td>Table Comments</td><td colspan="6"></td></tr>
<tr><td colspan="7">Columns</td></tr>
        <tr>
        <th>Name</th>
        <th>Data Type</th>
        <th>NOT NULL</th>
        <th>PK</th>
        <th>FK</th>
        <th>Default</th>
        <th>UNIQUE</th>
        <th>Comment</th>
        </tr>
<tr><td>person_id</td><td>SMALLINT(5)</td><td>Yes</td><td>Yes</td><td>Yes</td><td></td><td></td><td></td></tr>
<tr><td>post_id</td><td>SMALLINT(5)</td><td>Yes</td><td>Yes</td><td>Yes</td><td></td><td></td><td></td></tr>
<tr><td>ip</td><td>VARCHAR(55)</td><td>Yes</td><td>Yes</td><td>No</td><td></td><td></td><td></td></tr>
<tr><td>device</td><td>VARCHAR(45)</td><td>Yes</td><td>No</td><td>No</td><td></td><td></td><td></td></tr>
<tr><td>browser</td><td>VARCHAR(45)</td><td>Yes</td><td>No</td><td>No</td><td></td><td></td><td></td></tr>
<tr><td>deletedAt</td><td>DATETIME</td><td>No</td><td>No</td><td>No</td><td>NULL</td><td></td><td>Variavel de soft delete</td></tr>
<tr><td>instant</td><td>TIMESTAMP</td><td>Yes</td><td>No</td><td>No</td><td>CURRENT_TIMESTAMP</td><td></td><td>Momento da visualizacao</td></tr>
</table><a href="#home">Table List </a></br>
<a id="person_vote_post"></a><table style="width:100%"><caption>Table: person_vote_post </caption>
<tr><td>Table Comments</td><td colspan="6"></td></tr>
<tr><td colspan="7">Columns</td></tr>
        <tr>
        <th>Name</th>
        <th>Data Type</th>
        <th>NOT NULL</th>
        <th>PK</th>
        <th>FK</th>
        <th>Default</th>
        <th>UNIQUE</th>
        <th>Comment</th>
        </tr>
<tr><td>person_id</td><td>SMALLINT(5)</td><td>Yes</td><td>Yes</td><td>Yes</td><td></td><td></td><td></td></tr>
<tr><td>post_id</td><td>SMALLINT(5)</td><td>Yes</td><td>Yes</td><td>Yes</td><td></td><td></td><td></td></tr>
<tr><td>liked</td><td>SMALLINT(6)</td><td>Yes</td><td>No</td><td>No</td><td></td><td></td><td>1 é like, 0 é dislike</td></tr>
<tr><td>deletedAt</td><td>DATETIME</td><td>No</td><td>No</td><td>No</td><td>NULL</td><td></td><td>Variavel de soft delete</td></tr>
</table><a href="#home">Table List </a></br>
<a id="post"></a><table style="width:100%"><caption>Table: post </caption>
<tr><td>Table Comments</td><td colspan="6"></td></tr>
<tr><td colspan="7">Columns</td></tr>
        <tr>
        <th>Name</th>
        <th>Data Type</th>
        <th>NOT NULL</th>
        <th>PK</th>
        <th>FK</th>
        <th>Default</th>
        <th>UNIQUE</th>
        <th>Comment</th>
        </tr>
<tr><td>post_id</td><td>SMALLINT(5)</td><td>Yes</td><td>Yes</td><td>No</td><td></td><td></td><td></td></tr>
<tr><td>title</td><td>VARCHAR(45)</td><td>Yes</td><td>No</td><td>No</td><td></td><td>Yes</td><td></td></tr>
<tr><td>url</td><td>VARCHAR(45)</td><td>No</td><td>No</td><td>No</td><td>NULL</td><td></td><td>Url da imagem</td></tr>
<tr><td>content</td><td>VARCHAR(255)</td><td>Yes</td><td>No</td><td>No</td><td></td><td></td><td>Conteudo de texto</td></tr>
<tr><td>deletedAt</td><td>DATETIME</td><td>No</td><td>No</td><td>No</td><td>NULL</td><td></td><td>Variavel de soft delete</td></tr>
<tr><td>person_id</td><td>SMALLINT(5)</td><td>Yes</td><td>Yes</td><td>No</td><td></td><td></td><td></td></tr>
</table><a href="#home">Table List </a></br>
<a id="post_refere_bird"></a><table style="width:100%"><caption>Table: post_refere_bird </caption>
<tr><td>Table Comments</td><td colspan="6"></td></tr>
<tr><td colspan="7">Columns</td></tr>
        <tr>
        <th>Name</th>
        <th>Data Type</th>
        <th>NOT NULL</th>
        <th>PK</th>
        <th>FK</th>
        <th>Default</th>
        <th>UNIQUE</th>
        <th>Comment</th>
        </tr>
<tr><td>post_id</td><td>SMALLINT(5)</td><td>Yes</td><td>Yes</td><td>Yes</td><td></td><td></td><td></td></tr>
<tr><td>bird_name</td><td>VARCHAR(45)</td><td>Yes</td><td>Yes</td><td>Yes</td><td></td><td></td><td></td></tr>
<tr><td>deletedAt</td><td>DATETIME</td><td>No</td><td>No</td><td>No</td><td>NULL</td><td></td><td>Variavel de soft delete</td></tr>
</table><a href="#home">Table List </a></br>
<a id="post_refere_person"></a><table style="width:100%"><caption>Table: post_refere_person </caption>
<tr><td>Table Comments</td><td colspan="6"></td></tr>
<tr><td colspan="7">Columns</td></tr>
        <tr>
        <th>Name</th>
        <th>Data Type</th>
        <th>NOT NULL</th>
        <th>PK</th>
        <th>FK</th>
        <th>Default</th>
        <th>UNIQUE</th>
        <th>Comment</th>
        </tr>
<tr><td>post_id</td><td>SMALLINT(5)</td><td>Yes</td><td>Yes</td><td>Yes</td><td></td><td></td><td></td></tr>
<tr><td>person_id</td><td>SMALLINT(5)</td><td>Yes</td><td>Yes</td><td>Yes</td><td></td><td></td><td></td></tr>
<tr><td>deletedAt</td><td>DATETIME</td><td>No</td><td>No</td><td>No</td><td>NULL</td><td></td><td>Variavel de soft delete</td></tr>
</table><a href="#home">Table List </a></br>
</body></html>
