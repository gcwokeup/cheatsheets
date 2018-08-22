# Regex Cheatsheet

<table>
  <thead>
    <tr>
      <th>Social Security Number(SSN)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <table>
          <thead>
            <tr>
              <th>Type</th>
              <th>Regex</th>
              <th>Example</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>Without Dashes</td>
              <td> <code>^\d{9}$</code> </td>
              <td>123121234</td>
            </tr>
            <tr>
              <td>With Dashes</td>
              <td> <code>^\d{3}-\d{2}-\d{4}$</code></td>
              <td>123-12-1234</td>
            </tr>
            <tr>
              <td>With or Without Dashes</td>
              <td> <code>^\d{3}-\d{2}-\d{4}$|^\d{9}$</code></td>
              <td>123121234 or 123-12-1234</td>
            </tr> 
          </tbody>
        </table>
      </td>
    </tr>
  </tbody>
</table>
