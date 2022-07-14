<h3>ყველა ბრძანება, რომელიც მოქცეულია სერ ფონში, შეგყავთ ცალ-ცალკე!</h3> 

გარდა დასაწყისისა, სადაც უნდა ჩაწეროთ თქვენი node სახელი. 

<h3> კოდი არის ავტომატური ფუნქციონალის</h3>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto" data-snippet-clipboard-copy-content="wget -O stride.sh https://raw.githubusercontent.com/kj89/testnet_manuals/main/stride/stride.sh &amp;&amp; chmod +x stride.sh &amp;&amp; ./stride.sh"><pre class="notranslate"><code>wget -O stride.sh https://raw.githubusercontent.com/kj89/testnet_manuals/main/stride/stride.sh &amp;&amp; chmod +x stride.sh &amp;&amp; ./stride.sh
</div></code>

<div class="snippet-clipboard-content notranslate position-relative overflow-auto" data-snippet-clipboard-copy-content="source $HOME/.bash_profile"><pre class="notranslate"><code>source $HOME/.bash_profile
</code></pre></div>

<div class="snippet-clipboard-content notranslate position-relative overflow-auto" data-snippet-clipboard-copy-content="sudo systemctl daemon-reload
sudo systemctl enable strided
sudo systemctl restart strided &amp;&amp; sudo journalctl -u strided -f -o cat"><pre class="notranslate"><code>sudo systemctl daemon-reload
sudo systemctl enable strided
sudo systemctl restart strided &amp;&amp; sudo journalctl -u strided -f -o cat
</code></pre></div>

<div class="snippet-clipboard-content notranslate position-relative overflow-auto" data-snippet-clipboard-copy-content="strided status 2&gt;&amp;1 | jq .SyncInfo"><pre class="notranslate"><code>strided status 2&gt;&amp;1 | jq .SyncInfo
</code></pre></div>

<h3>საფულის შექმნა</h3>

ამ ბრძანების შემდგომ გამოტანილი ინფორმაცია აუცილებლად შეინახეთ გარე დოკუმენტში.

<div class="snippet-clipboard-content notranslate position-relative overflow-auto" data-snippet-clipboard-copy-content="strided keys add $WALLET"><pre class="notranslate"><code>strided keys add $WALLET
</code></pre></div>

საფულის აღდგენა
<div class="snippet-clipboard-content notranslate position-relative overflow-auto" data-snippet-clipboard-copy-content="strided keys add $WALLET --recover"><pre class="notranslate"><code>strided keys add $WALLET --recover
</code></pre></div>

საფულის ჩამონათვალი
<div class="snippet-clipboard-content notranslate position-relative overflow-auto" data-snippet-clipboard-copy-content="strided keys list"><pre class="notranslate"><code>strided keys list
</code></pre></div>

<h3> საფულის შენახვა </h3>

<div class="snippet-clipboard-content notranslate position-relative overflow-auto" data-snippet-clipboard-copy-content="STRIDE_WALLET_ADDRESS=$(strided keys show $WALLET -a)
STRIDE_VALOPER_ADDRESS=$(strided keys show $WALLET --bech val -a)
echo 'export STRIDE_WALLET_ADDRESS='${STRIDE_WALLET_ADDRESS} &gt;&gt; $HOME/.bash_profile
echo 'export STRIDE_VALOPER_ADDRESS='${STRIDE_VALOPER_ADDRESS} &gt;&gt; $HOME/.bash_profile
source $HOME/.bash_profile"><pre class="notranslate"><code>STRIDE_WALLET_ADDRESS=$(strided keys show $WALLET -a)
STRIDE_VALOPER_ADDRESS=$(strided keys show $WALLET --bech val -a)
echo 'export STRIDE_WALLET_ADDRESS='${STRIDE_WALLET_ADDRESS} &gt;&gt; $HOME/.bash_profile
echo 'export STRIDE_VALOPER_ADDRESS='${STRIDE_VALOPER_ADDRESS} &gt;&gt; $HOME/.bash_profile
source $HOME/.bash_profile
</code></pre></div>

<h3> საფულის შევსება </h3>
გაწევრიანდით დისქორდზე https://discord.gg/SdjQb3Zng8


გადადით token-faucet განყოფილებაში და შეიყვანეთ.



<div class="snippet-clipboard-content notranslate position-relative overflow-auto" data-snippet-clipboard-copy-content="$faucet:&lt;თქვენი_საფულის_მისამართი&gt;"><pre class="notranslate"><code>$faucet:&lt;თქვენი_საფულის_მისამართი&gt;
</code></pre></div>


საიტზე თქვენი მისამართით შეამოწმეთ დაირიცხა თუ არა ტოკენი.


https://poolparty.stride.zone/STRIDE


<h3>ვალიდატორის შექმნა</h3>

<div class="snippet-clipboard-content notranslate position-relative overflow-auto" data-snippet-clipboard-copy-content="strided tx staking create-validator \
  --amount 10000000ustrd \
  --from $WALLET \
  --commission-max-change-rate &quot;0.01&quot; \
  --commission-max-rate &quot;0.2&quot; \
  --commission-rate &quot;0.07&quot; \
  --min-self-delegation &quot;1&quot; \
  --pubkey  $(strided tendermint show-validator) \
  --moniker $NODENAME \
  --chain-id $STRIDE_CHAIN_ID"><pre class="notranslate"><code>strided tx staking create-validator \
  --amount 10000000ustrd \
  --from $WALLET \
  --commission-max-change-rate "0.01" \
  --commission-max-rate "0.2" \
  --commission-rate "0.07" \
  --min-self-delegation "1" \
  --pubkey  $(strided tendermint show-validator) \
  --moniker $NODENAME \
  --chain-id $STRIDE_CHAIN_ID
</code></pre></div>


გადადით ვებ-გვერდზე და შეამოწმეთ დაემატეთ თუ არა ვალიდატორად, თუ დაემატეთ თქვენი ლინკი ჩააგდეთ დისქორდზე "validators" განყოფილებაში ტექსტით "hello, can i get validator role? thanks. 
<თქვენი ვალიდატორის ლინკი>"

https://poolparty.stride.zone/STRIDE/staking

