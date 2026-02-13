  <h1>SQL Lesson 2: Queries with constraints (Pt. 1)</h1>

  <h2>Why do we need WHERE?</h2>
  <p>
    If a table has <strong>millions of rows</strong>, doing:
  </p>
  <pre><code>SELECT * FROM movies;</code></pre>
  <p>
    will show <em>everything</em> — messy and slow.
    So we use <code>WHERE</code> to tell SQL:
    <br />
    👉 “Give me only the rows that match my condition.”
  </p>

  <hr />

  <h2>Basic structure</h2>
  <pre><code>SELECT column, another_column
FROM mytable
WHERE condition;</code></pre>

  <p>Example:</p>
  <pre><code>SELECT title, year
FROM movies
WHERE year = 2010;</code></pre>

  <p>
    Meaning: ✅ Show movies <strong>only from 2010</strong>.
  </p>

  <hr />

  <h2>Using AND / OR</h2>

  <h3>AND = both conditions must be true</h3>
  <pre><code>SELECT title, year
FROM movies
WHERE year &gt;= 2000 AND year &lt;= 2010;</code></pre>
  <p>
    Meaning: Only movies between 2000 and 2010.
  </p>

  <h3>OR = any one condition can be true</h3>
  <pre><code>SELECT title
FROM movies
WHERE year = 2010 OR year = 2011;</code></pre>
  <p>
    Meaning: Movies from 2010 <strong>or</strong> 2011.
  </p>

  <hr />

  <h2>Useful operators (simple meaning)</h2>

  <table>
    <thead>
      <tr>
        <th>Operator</th>
        <th>What it means</th>
        <th>Example</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><code>=</code>, <code>!=</code>, <code>&lt;</code>, <code>&lt;=</code>, <code>&gt;</code>, <code>&gt;=</code></td>
        <td>Standard comparisons (equal / not equal / greater / smaller)</td>
        <td><code>WHERE rating != 4</code></td>
      </tr>
      <tr>
        <td><code>BETWEEN ... AND ...</code></td>
        <td>Value is inside a range (inclusive)</td>
        <td><code>WHERE year BETWEEN 2000 AND 2010</code></td>
      </tr>
      <tr>
        <td><code>NOT BETWEEN ... AND ...</code></td>
        <td>Value is outside a range</td>
        <td><code>WHERE year NOT BETWEEN 2000 AND 2010</code></td>
      </tr>
      <tr>
        <td><code>IN (...)</code></td>
        <td>Value must be one of the items in the list</td>
        <td><code>WHERE year IN (2000, 2005, 2010)</code></td>
      </tr>
      <tr>
        <td><code>NOT IN (...)</code></td>
        <td>Value must NOT be in the list</td>
        <td><code>WHERE year NOT IN (2000, 2005, 2010)</code></td>
      </tr>
    </tbody>
  </table>

  <hr />

  <h2>Why WHERE makes queries faster</h2>
  <p>
    Because the database doesn’t waste time returning rows you don’t need.
    <br />
    Less data returned = faster results.
  </p>

  <div class="note">
    <p><strong>Tip:</strong> SQL works even if you write keywords in small letters, but using capitals makes it easier to read.</p>
    <pre><code>SELECT * FROM movies;</code></pre>
  </div>

  <div class="warn">
    <p><strong>Devil’s advocate:</strong> A common beginner mistake is using a condition that is too broad.</p>
    <pre><code>WHERE year &gt; 1900</code></pre>
    <p>
      That still returns almost everything — so your query is still big and not very useful.
      The point of <code>WHERE</code> is to be specific.
    </p>
  </div>

  <h2>Exercise</h2>
  <p>
    Using the right constraints, find the information needed from the <code>Movies</code> table for each task.
    <br />
    (Paste the task text here and I can write the exact SQL queries for each one.)
  </p>


