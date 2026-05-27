<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0a1628,50:0a1628,100:0052ff&height=240&section=header&text=Oculus&fontSize=86&fontColor=ffffff&fontAlignY=38&desc=spending+guardrails+for+AI+agents+on+Solana&descAlignY=62&descSize=18&animation=fadeIn" width="100%" alt="Oculus banner"/>

<br/>

<a href="https://oculusagent.xyz">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=22&pause=1000&color=0052FF&center=true&vCenter=true&width=860&lines=on-chain+policy+enforcement;every+tx+checked+before+settlement;automatic+USDC+refund+on+breach;built+for+Solana+AI+agents" alt="typing"/>
</a>

<br/><br/>

<a href="https://oculusagent.xyz"><img src="https://img.shields.io/badge/site-oculusagent.xyz-0052ff?style=flat-square&labelColor=0a1628" alt="site"/></a>
<a href="https://github.com/OculusAgent?tab=followers"><img src="https://img.shields.io/github/followers/useoculus?style=flat-square&color=0052ff&labelColor=0a1628&label=followers" alt="followers"/></a>
<a href="https://github.com/OculusAgent/oculus-program/stargazers"><img src="https://img.shields.io/github/stars/useoculus/oculus-program?style=flat-square&color=0052ff&labelColor=0a1628&label=stars" alt="stars"/></a>

</div>

<br/>

## What is Oculus?

Oculus is a **policy enforcement layer** for AI agent wallets on Solana. Every outbound transaction is checked against an on-chain spending policy before it settles — if the agent attempts to spend more than its daily limit, the transaction is rejected at the program level and an automatic USDC refund is queued within 60 seconds.

The agent doesn't need to be smarter. It needs a policy.

<br/>

## ⌬ &nbsp; the stack

| Repo | Purpose | Language |
|------|---------|----------|
| [oculus-program](https://github.com/OculusAgent/oculus-program) | On-chain policy enforcement | Rust / Anchor |
| [oculus-sdk](https://github.com/OculusAgent/oculus-sdk) | TypeScript SDK for agent integration | TypeScript |
| [oculus-webhook](https://github.com/OculusAgent/oculus-webhook) | Helius webhook ingestor + refund queue | Python / FastAPI |

<br/>

## ⌬ &nbsp; flow

```
agent ──► proposes tx ──► oculus-sdk.checkSpend ──► oculus-program.check_spend
                                                          │
                              ┌───── SpendChecked ◄───────┤
                              │                           │
                              ▼                  LimitBreached
                       tx proceeds                       │
                                                         ▼
                                            helius webhook ──► reimbursement queue
                                                                       │
                                                                       ▼
                                                              USDC refund < 60s
```

<br/>

## ⌬ &nbsp; stats

<div align="center">
<img height="170" src="https://github-readme-stats.vercel.app/api?username=useoculus&show_icons=true&theme=transparent&hide_border=true&bg_color=0a1628&title_color=0052ff&icon_color=0052ff&text_color=ffffff&include_all_commits=true&rank_icon=github"/>
<img height="170" src="https://github-readme-stats.vercel.app/api/top-langs/?username=useoculus&layout=compact&theme=transparent&hide_border=true&bg_color=0a1628&title_color=0052ff&text_color=ffffff&langs_count=6"/>
</div>

<br/>

## ⌬ &nbsp; learn more

- **Site:** [oculusagent.xyz](https://oculusagent.xyz)
- **Docs:** [oculusagent.xyz/docs](https://oculusagent.xyz/docs)

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0052ff,50:0a1628,100:0a1628&height=100&section=footer&animation=fadeIn" width="100%" alt="footer"/>
</div>
