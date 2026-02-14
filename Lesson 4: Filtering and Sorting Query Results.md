

  <h1>SQL Lesson 4: Filtering and Sorting Query Results</h1>

  <h2>1) DISTINCT – Removing Duplicate Results</h2>

  <p>
    Even though the data in a database may be unique, the results of a query may not be.
    For example, many movies can be released in the same year.
  </p>

  <p>
    SQL provides the <code>DISTINCT</code> keyword to remove duplicate rows
    from the results.
  </p>

  <h3>Select Query with Unique Results</h3>

  <pre><code>SELECT DISTINCT column, another_column, …
FROM mytable
WHERE condition(s);</code></pre>

  <div class="note">
    <strong>Note:</strong><br>
    <code>DISTINCT</code> removes duplicate rows automatically.
    In future lessons, you will learn how to handle duplicates more specifically using
    the <code>GROUP BY</code> clause.
  </div>

  <hr>

  <h2>2) ORDER BY – Sorting Results</h2>

  <p>
    In real databases, data is not stored in a neat order.
    As the table grows to thousands or millions of rows,
    it becomes difficult to read without sorting.
  </p>

  <p>
    The <code>ORDER BY</code> clause allows you to sort results
    in ascending or descending order.
  </p>

  <h3>Select Query with Ordered Results</h3>

  <pre><code>SELECT column, another_column, …
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC;</code></pre>

  <ul>
    <li><strong>ASC</strong> – Ascending order (A → Z, 1 → 10)</li>
    <li><strong>DESC</strong> – Descending order (Z → A, 10 → 1)</li>
  </ul>

  <div class="info">
    When <code>ORDER BY</code> is used, each row is sorted alpha-numerically
    based on the column's value.
    Some databases also allow collation settings for better international text sorting.
  </div>

  <hr>

  <h2>3) LIMIT and OFFSET – Restricting Results</h2>

  <p>
    Often you don’t need all rows from a table.
    You may only want the first few results or a specific "page" of results.
  </p>

  <ul>
    <li><code>LIMIT</code> – Number of rows to return</li>
    <li><code>OFFSET</code> – Number of rows to skip before returning results</li>
  </ul>

  <h3>Select Query with Limited Rows</h3>

  <pre><code>SELECT column, another_column, …
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC
LIMIT num_limit OFFSET num_offset;</code></pre>

  <p>
    Websites like Reddit or Pinterest use this concept for pagination:
  </p>

  <ul>
    <li>Page 1 → <code>LIMIT 10 OFFSET 0</code></li>
    <li>Page 2 → <code>LIMIT 10 OFFSET 10</code></li>
    <li>Page 3 → <code>LIMIT 10 OFFSET 20</code></li>
  </ul>

  <div class="note">
    <strong>Did you know?</strong><br>
    <code>LIMIT</code> and <code>OFFSET</code> are generally applied last,
    after filtering (<code>WHERE</code>) and sorting (<code>ORDER BY</code>).
    You will learn more about query execution order in Lesson 12.
  </div>

</body>
</html>
