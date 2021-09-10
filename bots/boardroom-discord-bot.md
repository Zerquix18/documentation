---
description: A Discord bot to connect to Boardroom
---

# Boardroom Discord Bot

The **Boardroom Discord Bot** uses the [Boardroom API ](../boardroom-api/boardroom-api.md)to bring governance data right into your Discord server. This allows members of your server to request governance information and be notified of any changes. This includes:

* Displaying Boardroom's supported protocols
* Displaying the proposals in a particular protocol
* Displaying the details of a particular proposal
* Checking the voters for a protocol proposal
* Checking the proposals a particular voter has participated in
* Displaying global statistics

You can also subscribe to this information and be notified when it changes.

### Adding the Discord Bot to Your Server

You can add the discord bot to your server by [clicking here](https://discord.com/api/oauth2/authorize?client_id=873193852184453172&permissions=2147485696&scope=applications.commands%20bot).

### Available Commands

You can type /command\_name to use a command.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Command</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Parameters</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">protocol_list</td>
      <td style="text-align:left">Lists all protocols supported by Boardroom.</td>
      <td style="text-align:left">&lt;code&gt;&lt;/code&gt;</td>
    </tr>
    <tr>
      <td style="text-align:left">protocol_proposals</td>
      <td style="text-align:left">Lists all proposals in a protocol.</td>
      <td style="text-align:left"><code>cname</code> (required) - Code name for the protocol must be [a-z0-9]
        (e.g &quot;uniswap&quot;</td>
    </tr>
    <tr>
      <td style="text-align:left">protocol_voters</td>
      <td style="text-align:left">Lists all voters in a protocol.</td>
      <td style="text-align:left"><code>cname</code> (required) - Code name for the protocol must be [a-z0-9]
        (e.g &quot;uniswap&quot;</td>
    </tr>
    <tr>
      <td style="text-align:left">proposal_votes</td>
      <td style="text-align:left">Lists all votes in a protocol.</td>
      <td style="text-align:left">
        <p></p>
        <p><code>refid</code> (required) - Unique code representing proposal (ends
          with =)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">protocol_get</td>
      <td style="text-align:left">Retrieves information about a specific protocol.</td>
      <td style="text-align:left">
        <p></p>
        <p><code>cname</code> (required) - Code name for the protocol must be [a-z0-9]
          (e.g &quot;uniswap&quot;)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">proposal_get</td>
      <td style="text-align:left">Retrieves information about a specific proposal.</td>
      <td style="text-align:left"><code>refid</code> (required) - Unique code representing proposal (ends
        with =)</td>
    </tr>
    <tr>
      <td style="text-align:left">voters_votes</td>
      <td style="text-align:left">Retrieves the votes of a specific address.</td>
      <td style="text-align:left"><code>address</code> (required) - Address of the voter</td>
    </tr>
    <tr>
      <td style="text-align:left">voters_get</td>
      <td style="text-align:left">Retrieves information about a voter.</td>
      <td style="text-align:left"><code>address</code> (required) - Address of the vote</td>
    </tr>
    <tr>
      <td style="text-align:left">stats</td>
      <td style="text-align:left">Prints Boardroom&apos;s global statistics.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">subscribe_to_protocols</td>
      <td style="text-align:left">Be notified any time a new protocol is added.</td>
      <td style="text-align:left"><code>frequency</code> - How often to check (in hours). Default is 15 minutes
        (0.25)</td>
    </tr>
    <tr>
      <td style="text-align:left">subscribe_to_protocol_proposals</td>
      <td style="text-align:left">Be notified any time a new proposal is added.</td>
      <td style="text-align:left">
        <p><code>cname</code> (required) - Code name for the protocol must be [a-z0-9]
          (e.g &quot;uniswap&quot;)</p>
        <p><code>frequency</code> - How often to check (in hours). Default is 15 minutes
          (0.25)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">subscribe_to_proposal_state</td>
      <td style="text-align:left">Be notified any time the state of a proposal changes.</td>
      <td style="text-align:left">
        <p><code>refid</code> (required) - Unique code representing proposal (ends
          with =)</p>
        <p><code>frequency</code> - How often to check (in hours). Default is 15 minutes
          (0.25)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">subscribe_to_proposal_votes</td>
      <td style="text-align:left">Be notified any time a proposal has a new vote.</td>
      <td style="text-align:left">
        <p><code>refid</code> (required) - Unique code representing proposal (ends
          with =)</p>
        <p><code>frequency</code> - How often to check (in hours). Default is 15 minutes
          (0.25)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">subscribe_to_voter_votes</td>
      <td style="text-align:left">Be notified any time an address votes.</td>
      <td style="text-align:left">
        <p></p>
        <p><code>address</code> (required) - Address of the voter</p>
        <p><code>frequency</code> - How often to check (in hours). Default is 15 minutes
          (0.2</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">subscribe_to_stats</td>
      <td style="text-align:left">Displays global statistics from time to time.</td>
      <td style="text-align:left"><code>frequency</code> - How often to check (in hours). Default is 15 minutes
        (0.25)</td>
    </tr>
    <tr>
      <td style="text-align:left">show_all_subscriptions</td>
      <td style="text-align:left">Lists all active subscriptions, including their number which allows to
        delete them.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">delete_subscription</td>
      <td style="text-align:left">
        <p></p>
        <p>Deletes a subscription
          <br />
        </p>
      </td>
      <td style="text-align:left">
        <p></p>
        <p><code>number</code> - Subscription number which you can get from <code>/show_all_subscriptions</code>.
          This corresponds to an index.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">delete_all_subscriptions</td>
      <td style="text-align:left">Delete all subscriptions.</td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

