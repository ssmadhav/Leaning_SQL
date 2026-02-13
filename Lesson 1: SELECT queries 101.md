  <h1> SQL Lesson 1: SELECT queries 101 </h1>

  <h2>What is a SELECT query?</h2>
  <p>
    A <strong>SELECT query</strong> is just a way of telling the database:
    <br />
    👉 “Hey, give me this data from that table.”
  </p>

  <h2>Think of a Table Like This</h2>
  <p>
    Imagine a table called <code>Dogs</code>.
  </p>
  <ul>
    <li><strong>Each row</strong> = one dog (one item)</li>
    <li><strong>Each column</strong> = a property/info about the dog</li>
  </ul>

  <table>
    <thead>
      <tr>
        <th>Name</th>
        <th>Breed</th>
        <th>Color</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Max</td>
        <td>Pug</td>
        <td>Brown</td>
      </tr>
      <tr>
        <td>Luna</td>
        <td>Beagle</td>
        <td>White</td>
      </tr>
    </tbody>
  </table>

  <p>
    Same idea applies to a <code>Movies</code> table:
  </p>
  <ul>
    <li><strong>Row</strong> = one movie</li>
    <li><strong>Column</strong> = details like title, year, director, rating</li>
  </ul>

  <h2>Basic SELECT (Specific Columns)</h2>
  <p>
    If you want only certain columns:
  </p>
  <pre><code>SELECT column, another_column
FROM mytable;</code></pre>

  <p>Example:</p>
  <pre><code>SELECT title, year
FROM Movies;</code></pre>

  <p>
    This means: “Give me only the movie <strong>title</strong> and <strong>year</strong>.”
  </p>

  <h2>SELECT All Columns</h2>
  <p>
    If you want everything from the table, use <code>*</code>:
  </p>
  <pre><code>SELECT *
FROM mytable;</code></pre>

  <p>Example:</p>
  <pre><code>SELECT *
FROM Movies;</code></pre>

  <p>
    <code>*</code> means: “Give me all columns.”
  </p>

  <h2>When Should You Use <code>*</code>?</h2>
  <div class="note">
    <p><strong>Good for:</strong></p>
    <ul>
      <li>Checking what’s inside a table</li>
      <li>Exploring the table structure</li>
    </ul>
    <p><strong>Not always good for:</strong></p>
    <ul>
      <li>Real applications</li>
      <li>Large databases</li>
    </ul>
    <p>
      Reason: If a table has many columns and you only need 1–2, using <code>*</code>
      pulls unnecessary data and can slow things down.
    </p>
  </div>

  <h2>What a Query Really Tells</h2>
  <p>A query usually describes:</p>
  <ol>
    <li><strong>What</strong> data you want</li>
    <li><strong>From where</strong> (which table)</li>
    <li>Sometimes <strong>how</strong> to filter/sort it</li>
  </ol>

  <p>Example:</p>
  <pre><code>SELECT title
FROM Movies;</code></pre>

  <p>
    Meaning:
  </p>
  <ul>
    <li>What → <code>title</code></li>
    <li>From → <code>Movies</code></li>
  </ul>

  <h2>Quick Challenge</h2>
  <p>
    Try writing these queries:
  </p>
  <ul>
    <li>Show only movie names</li>
    <li>Show only directors</li>
    <li>Show movie name and rating</li>
  </ul>

</body>
</html>
