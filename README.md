# statePattern
<b>Lab Seatwork 2: Bank Account State</b>

<p>
  A bank needs to manage different states of customer accounts, including active, suspended, and closed. Each state has specific rules and restrictions regarding allowed operations, and accounts have associated attributes like account number and balance.
  <ul>
    <li><b>Active accounts:</b> Allow deposits and withdrawals.</li>
    <li><b>Suspended accounts:</b> Disallow deposits and withdrawals transactions, but allow viewing account information.</li>
    <li><b>Closed accounts:</b> Disallow all transactions and viewing of account information.</li>
  </ul>
</p>

<p>
  Currently, the system relies on conditional statements within the Account class to check the account state and determine valid actions. This approach becomes cumbersome and error-prone as the number of states and their associated logic grows.
  
  Implement the State pattern to improve code maintainability and flexibility:
  <ol>
    <li><b>Define Account States:</b> Create separate classes representing different account states: ActiveState, SuspendedState, and ClosedState.</li>
    <li><b>Implement State Interface:</b> Define an interface AccountState with methods for common actions like deposit, withdraw, activate, suspend, and close.</li>
    <li><b>Implement State Behaviors:</b> Each concrete state class implements the AccountState interface, providing specific behavior for its respective state. For example, the ActiveState class would allow deposits and withdrawals, while the ClosedState wouldn't allow any transactions.</li>
    <li><b>Update Account Class:</b></li>
      <ul>
        <li>Include attributes for accountNumber and balance.</li>
        <li>Remove state-specific logic from the Account class.</li>
        <li>Introduce a reference to the current AccountState object.</li>
        <li>Delegate actions like deposit, withdraw, activate, suspend, and close to the current state object through its corresponding methods.</li>
      </ul>
  </ol>
</p>

<p><b>Logic:</b>
  <ul>
    <li><b>If the account is active:</b>
      <ul>
        <li>You can either suspend it or close it.</li>
      </ul>
    </li>
    <li><b>If the account is suspended:</b>
      <ul>
        <li>You can either activate or close it.</li>
        <li>No deposits and withdrawals allowed.</li>
      </ul>
    </li>
    <li><b>If the account is closed:</b>
      <ul>
        <li>You can neither suspend nor activate it.</li>
        <li>No deposits and withdrawals allowed.</li>
      </ul>
    </li>
  </ul>
</p>

<p><b>Composition of Account:</b>
  <ul>
    <li><b>accountNumber:</b> String</li>
    <li><b>balance:</b> Double</li>
    <li><b>accountState:</b> AccountState</li>
  </ul>
</p>

<p><b>Methods:</b>
  <ul>
    <li><b>deposit(Double depositAmount):</b> void</li>
    <li><b>withdraw(Double withdrawAmount)::</b> void</li>
    <li><b>suspend():</b> void</li>
    <li><b>activate():</b> void</li>
    <li><b>close():</b> void</li>
    <li><b>toString()</b> // displays account number and balance</li>
  </ul>
</p>

<p><b>Note:</b> No if-else, switch will be used</p>
<p>See AccountTest() class to test the Account.</p>
