<template>
  <el-tabs class="collapse-tabs" v-model="activeName" @tab-click="handleClick">
    <el-tab-pane label="Backup and Inheritance" name="first">
      <el-collapse v-model="activeNames" @change="handleChange" accordion>
        <el-collapse-item title="What is the difference between a backup and an inheritance?" name="1">
          <div>With a backup, control over the wallet transfers to the backup wallet, while the currency itself does not get moved to the other wallet, and only the ownership of the currency is transferred from one wallet to the other. In fact, all the settings are transferred from one wallet to the other. For example, if there is a trust fund, it will appear in the backup wallet and the owner of the backup wallet will be able to cancel it. With an inheritance, funds are physically transferred to external wallets. If a trust fund exists, it will not be transferred to external wallets, but will continue to be operated from the original wallet.</div>
        </el-collapse-item>
        <el-collapse-item title="Does anyone have control over the smart contract?" name="2">
          <div>Only the wallet owner has control!</div>
        </el-collapse-item>
        <el-collapse-item title="What happens if I lose the seed to both my wallet and my backup wallet?" name="3">
          <div>Firstly, the chance of such an event is significantly lower than the chance of a single loss. Secondly, the backup wallet can be saved in a number of ways that are less secure than how you would keep the see of the main wallet, since even if someone were to gain control over the backup wallet, there would be no money in it unless a backup event had occurred. In addition, if you configure a combination of backup and inheritance, and the time period for the inheritance has passed, it will be triggered. We are planning to support a number of backup wallets in the future. Alternatively, the possibility of collaborating with leading law firms or accountants that the user will be able to contact and define their wallet as a third level and higher backup wallet, is being examined. In addition, the setting of their wallet (by the owner of the wallet only) as a backup wallet in the event of a catastrophe, which, of course involves reliance on a third party rather than on the blockchain, would be at the discretion of the user.</div>
        </el-collapse-item>
        <el-collapse-item title="Can I send money directly to my backup?" name="4">
          <div>Yes, of course, this is a wallet for all intents and purposes, so you can send money directly to it.</div>
        </el-collapse-item>
        <el-collapse-item title="Can I send coins directly from the backup to an external wallet?" name="5">
          <div>Yes, definitely, it’s a wallet for all intents and purposes.</div>
        </el-collapse-item>
        <el-collapse-item title="Are funds that are sent directly to the smart wallet also backed up?" name="6">
          <div>Any configuration that the smart wallet owner has set applies to all funds; that is, if a backup or inheritance is configured, or a combination of the two, this setting will apply to all funds in the wallet regardless of when they were received.</div>
        </el-collapse-item>
        <el-collapse-item title="What is the difference between the seed of the primary wallet and the see of the backup wallet?" name="7">
          <div>There is no connection between the two – these are two completely different wallets. The main difference is the level of security that every seed requires, while the seed of the main wallet allows access to all the funds immediately (and therefore should be kept with extreme care). The seed of the backup wallet actually does not allow access to the funds at all. Only in the event of a backup does the above-mentioned wallet control the funds, and therefore the seed can be maintained at a lower level of protection, that is, shared with family members, lawyers, etc.</div>
        </el-collapse-item>
        <el-collapse-item title="Will the beneficiary of the inheritance know about the inheritance before it passes to him or her?" name="8">
          <div>No, not necessarily. On the one hand, it would be very difficult to hide it if they were to actively search, since all the data is on the blockchain. On the other hand, even if they knows that they have an inheritance wallet, they would have no way of knowing who bequeathed it.</div>
        </el-collapse-item>
        <el-collapse-item title="Can I backup any cryptocurrency?" name="9">
          <div>At this stage, you can backup ETH and any ETH-based currency, i.e., ERC20. In the near future, we will open the system to additional blockchains and enable additional currencies.</div>
        </el-collapse-item>
        <el-collapse-item title="Can I set up a backup and parallel inheritance?" name="10">
          <div>Yes, absolutely, and it’s even recommended. You can set up a backup for a short time, for example a backup that will be activated if there is no activity in the wallet for a month, and then set up an inheritance if the backup wallet is inactive for a year or two.</div>
        </el-collapse-item>
        <el-collapse-item title="Are my funds locked after transferring to the smart contract? In other words, suppose I created a backup or inheritance, and now I want to send money to the marketplace, do I need to cancel the backup or the inheritance?" name="11">
          <div>No! Funds are not locked – it is a smart wallet, to which funds can be added or removed without having to cancel or reset the backup or inheritance. Any amount sent to the wallet is automatically backed up or defined as inheritance.</div>
        </el-collapse-item>
      </el-collapse>
    </el-tab-pane>
    <el-tab-pane label="Cost of the Service" name="second">
      <el-collapse v-model="activeNames" @change="handleChange" accordion>
        <el-collapse-item title="What is the cost of the service?" name="1">
          <div>You determine the cost of the service during a backup/inheritance event, fixed payments,trust fund, etc. There are operators (similar to miners) that will activate the smart contract. The payment you set will be transferred directly to the contract operator.</div>
        </el-collapse-item>
        <el-collapse-item title="Does Kirobo get compensated for service activations?" name="2">
          <div>No! The only one who receives payment is the service operator (similar to miners), who will decide whether it is worthwhile to operate the service according to supply and demand, and its direct costs.</div>
        </el-collapse-item>
        <el-collapse-item title="Is a situation possible in which I put in an insufficient sum and the operator has not activated the service for me?" name="3">
          <div>Yes, it is possible for this situation to occur. In order to prevent this, we added a “measuring clock” that examines the cost of services – the average price offered by other users – and takes into account additional parameters. This clock allows you to know whether the amount you allocated is sufficient for the execution of the action.</div>
        </el-collapse-item>
        <el-collapse-item title="What can I do to prevent a situation in which even though I have deposited enough Kirobo , the operator does not activate the service (because of lack of profitability) and therefore a backup is not carried out or my heirs do not receive their inheritance?" name="4">
          <div>When setting up an inheritance/backup, you can set up a “safety net” depending on the amount of Kirobo actually in your wallet. For example, when you create the backup, you decide to give 100 Kirobo to the “operator” and you want to set another 1,000 KIROBO as a safety net. You can divide the safety net into packets, for example, if 3 time slots passed then 300 Kirobo of the 1000 in the safety net will transfer to the reward and if another 5 time slots pass, another 700 Kirobo will transfer to the reward.</div>
        </el-collapse-item>
        <el-collapse-item title="Are the funds I have defined as a &quot;safety net&quot; locked like the &quot;reward&quot; that I have defined?" name="5">
          <div>No! After setup you can use your funds however you like.</div>
        </el-collapse-item>
        <el-collapse-item title="What happens if a (backup/inheritance) occurs, but I had already used the safety net funds?" name="6">
          <div>In this case, you can send the same amount of Kirobo to your wallet that you had set up as a safety net.</div>
        </el-collapse-item>
      </el-collapse>
    </el-tab-pane>
    <el-tab-pane label="Operators (similar to miners)" name="third">
      <el-collapse v-model="activeNames" @change="handleChange" accordion>
        <el-collapse-item title="Who can be an &quot;operator&quot;?" name="1">
          <div>Anyone can act as an “operator”. If the operator offers a price (BID) on a time slot, and wins, he may activate all the contracts in the same time slot and win the rewards of all those contracts.</div>
        </el-collapse-item>
        <el-collapse-item title="If the operator checks viability according to the general time slot compensation, what prevents me from offering a really low price knowing that the operator calculates the time slot not contract by contract, but rather according to the number of contracts on that time slot?" name="2">
          <div>There are a limited number of “operators” on any time slot. When the system operates at full capacity, not all operators will be able to operate all contracts and therefore will focus only on contracts that will offer them the highest reward, so that one who offers an average or higher reward knows they have a very high probability the operator will perform the operation for him, but whoever offers a low reward, will have his operation postponed to the next time slot, and at the next time slot, the operator of that time slot will perform the same calculation regarding whether it is worthwhile for him to operate or not, considering that he can run only a limited amount in any time slot.</div>
        </el-collapse-item>
        <el-collapse-item title="Can an operator change the settings in a smart contract and send my currency to another wallet not within my control?" name="3">
          <div>No, a smart contract cannot be changed from the moment it is deployed in the blockchain network. The only thing the operator can do is simply ask the smart contract to check itself (this involves payment) and activate itself according to predefined rules. It is impossible to change the rules in a smart contract.</div>
        </el-collapse-item>
      </el-collapse>
    </el-tab-pane>
    <el-tab-pane label="Kirobo Tokens" name="fourth">
      <el-collapse v-model="activeNames" @change="handleChange" accordion>
        <el-collapse-item title="Why do we need Kirobo? Why not just allow payment in ETH?" name="1">
          <div>As we explained, the operator who operates the contracts will receive very high compensation, so if we allow payment in ETH, the operators will pay a lot of GAS in order to activate the contract first, which will cause the operator who paid less GAS to activate the contract a second after the first (which will not be rewarded) causing unnecessary operations that will overload the ETH network and make the process much more expensive, and there is no reason to run the contract at such speed and cost. To prevent this, we added time slots. Only the time slot winner can activate the contract anytime during the time slot, ensuring that the BID that the operator offers for that time slot is relevant to the true cost of the service, as well as to the real supply and demand of the system. This will prevent unnecessary loads on the blockchain network, prevent paying too much GAS, and will increase actions (backup/inheritance, etc.) that are not related to the action itself, but stems from the operator’s desire to “hit the jackpot”.</div>
        </el-collapse-item>
      </el-collapse>
    </el-tab-pane>
    <el-tab-pane label="Other" name="five">
      <el-collapse v-model="activeNames" @change="handleChange" accordion>
        <el-collapse-item title="Do I have to use Kirobo's wallet or can I use my wallet such as Ledger or Trezor?" name="1">
          <div>You do not have to use Kirobo’s wallet. You can use Ledger, Trezor, and even Metamask and connect to your smart wallet, (just like connecting to MyEtherWallet) which would operate the smart contract with the payment you defined transferred directly to the contract operator. Your cold wallet becomes a smart wallet.</div>
        </el-collapse-item>
        <el-collapse-item title="I understand that through this system, you can prevent a robber from robbing me. How does that work?" name="2">
          <div>Via several methods: A. Placing a time limit on the transfer of large amounts, with the option of canceling the limit. Cancellation of the restriction will take effect after a period of time defined by the wallet owner (e.g. 72 hours). B. Set up an extra wallet for everyday use. Your daily wallet will have a daily limit and will only show a portion of the total amount. It will be safe to use both in terms of its visibility and limited transfer capability. In the main wallet, settings can be changed and large amounts of money can be sent. Naturally the main wallet will be in a safe place and will be used rarely. The daily wallet will be used as cash and will always be physically available. C. Define a wallet for large transfers. For example, up to $ 2,000 can be sent directly from the main wallet, but a higher amount must be sent to another predefined wallet (another wallet owned by the user, a family member’s wallet, etc.), and only from the secondary wallet can an amount larger than $2000 be sent.</div>
        </el-collapse-item>
      </el-collapse>
    </el-tab-pane>
  </el-tabs>
</template>

<script>
export default {
  data() {
    return {
      activeName: "first"
    };
  }
};
</script>

<style>
.collapse-tabs {
  width: 90%;
}
.el-tabs__item {
  color: white;
  font-size: 1.2em;
}
.el-collapse-item__header,
.el-collapse-item__wrap {
  background: transparent;
  color: white;
}
.el-collapse {
  border: none;
}
.el-collapse-item {
  color: white;
}
.el-collapse-item__header {
  height: auto;
  font-weight: bold;
  font-size: 16px;
  border: none;
}
.el-collapse-item__content {
  font-size: 14px;
  color: rgba(255, 255, 255, 0.9);
}
.el-collapse-item__header.is-active {
  color: #31cbfe;
}
.el-tabs__item.is-active {
  color: #31cbfe;
}
.el-tabs__active-bar {
  background-color: #31cbfe;
}
</style>
