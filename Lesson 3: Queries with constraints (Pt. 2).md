  <h1>SQL Lesson 3: Queries with constraints (Pt. 2)</h1>

  <h2>Text-based filtering with WHERE</h2>
  <p>
    When writing <code>WHERE</code> clauses with columns that contain text,
    SQL provides useful operators for:
  </p>

  <ul>
    <li>Case-sensitive comparison</li>
    <li>Case-insensitive comparison</li>
    <li>Wildcard pattern matching</li>
  </ul>

  <hr />

  <h2>Common Text Operators</h2>

  <table>
    <thead>
      <tr>
        <th>Operator</th>
        <th>Condition</th>
        <th>Example</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><code>=</code></td>
        <td>Case-sensitive exact match</td>
        <td><code>col_name = "abc"</code></td>
      </tr>
      <tr>
        <td><code>!=</code> or <code>&lt;&gt;</code></td>
        <td>Case-sensitive inequality</td>
        <td><code>col_name != "abcd"</code></td>
      </tr>
      <tr>
        <td><code>LIKE</code></td>
        <td>Case-insensitive match</td>
        <td><code>col_name LIKE "ABC"</code></td>
      </tr>
      <tr>
        <td><code>NOT LIKE</code></td>
        <td>Case-insensitive inequality</td>
        <td><code>col_name NOT LIKE "ABCD"</code></td>
      </tr>
      <tr>
        <td><code>%</code></td>
        <td>Matches zero or more characters (used with LIKE)</td>
        <td><code>col_name LIKE "%AT%"</code></td>
      </tr>
      <tr>
        <td><code>_</code></td>
        <td>Matches exactly one character (used with LIKE)</td>
        <td><code>col_name LIKE "AN_"</code></td>
      </tr>
      <tr>
        <td><code>IN (...)</code></td>
        <td>String exists in list</td>
        <td><code>col_name IN ("A", "B", "C")</code></td>
      </tr>
      <tr>
        <td><code>NOT IN (...)</code></td>
        <td>String does not exist in list</td>
        <td><code>col_name NOT IN ("D", "E", "F")</code></td>
      </tr>
    </tbody>
  </table>

  <hr />

  <h2>Wildcard Examples Explained</h2>

  <h3>Using %</h3>
  <pre><code>col_name LIKE "%AT%"</code></pre>
  <p>This matches:</p>
  <ul>
    <li>AT</li>
    <li>ATTIC</li>
    <li>CAT</li>
    <li>BATS</li>
  </ul>

  <h3>Using _</h3>
  <pre><code>col_name LIKE "AN_"</code></pre>
  <p>This matches:</p>
  <ul>
    <li>AND</li>
  </ul>
  <p>But NOT:</p>
  <ul>
    <li>AN</li>
    <li>ANGLE</li>
  </ul>

  <hr />

  <div class="note">
    <strong>Did you know?</strong><br />
    All strings must be wrapped in quotes so SQL knows it is text
    and not a column name or keyword.
  </div>
  
<br>

  <div class="info">
    <strong>Important:</strong><br />
    While SQL supports text searching, large-scale full-text search is better handled
    by dedicated tools like Apache Lucene or Sphinx.
    These systems are optimized for advanced search features,
    internationalization, and better performance.
  </div>

  <hr />

  <h2>Query Structure Reminder</h2>

  <pre><code>SELECT column, another_column
FROM mytable
WHERE condition
    AND/OR another_condition;</code></pre>

  <hr />

  <h2>Exercise</h2>
  <p>
    Try writing queries using the operators above to filter the
    results based on the tasks in your lesson.
  </p>

</body>
</html>
