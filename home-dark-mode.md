---
title: KongAir Demo
description:
---

::page-hero
---
title-font-size: 64px
title-line-height: 76px
title-font-weight: normal
description-font-size: 18px
description-line-height: 28px
description-font-weight: normal
color: #022841
padding: 40px 0
image:
  src: 'https://github.com/travisterwilligar/kongair-template/blob/main/images/dark-mode/travel.png?raw=true'
  position: right
  max-width: 45%
styles: |

  background: radial-gradient(74.91% 63.06% at 0% -5.79%, #025D99 0%, #000 100%);
  margin-bottom: -100px!important;
---
#title
Build the future of air travel with [KongAir]{style="font-weight: 600;"} APIs

#description
Tools for developers to automate interactions with KongAir

#actions
  ::k-button{ size="large" to="/apis" style="margin-right: 10px" }
  API reference
  ::
  ::k-button{ size="large" appearance="secondary" to="/apis" }
  Learn more
  ::
::

::page-section
---
full-width: true
styles: |
  background: no-repeat center url('https://raw.githubusercontent.com/travisterwilligar/kongair-template/refs/heads/main/images/dark-mode/plane-divider.svg')
  background-size: contain
---
::

::page-hero
---
title-font-size: 32px
title-line-height: 42px
description-font-size: 18px
title-font-weight: normal
description-font-weight: normal
image:
  max-width: 50%
  src: 'https://raw.githubusercontent.com/travisterwilligar/kongair-template/refs/heads/main/images/dark-mode/code-sample.svg'
padding: 50px 20px
styles: |
  img {
    box-shadow: 0px 0px 89px rgba(0, 0, 0, 0.1);
    border-radius: 20px;
  }
---
#title
Kickstart development with [easy APIs]{style="font-weight: 700;"}
#description
Our APIs are dead simple to use and support industry standard SLAs.

#actions
  ::k-button{ size="large" appearance="secondary" to="/apis" }
  <svg width="20px" height="20px">
  <image xlink:href="https://raw.githubusercontent.com/travisterwilligar/kongair-template/refs/heads/main/images/dark-mode/terminal-window.svg" />
  </svg>
  Try it for free
  ::
::

::page-section
---
padding: 50px 0
styles: |
  background: no-repeat top url('https://raw.githubusercontent.com/travisterwilligar/kongair-template/refs/heads/main/images/dark-mode/plane-bg.svg'), linear-gradient(287deg, rgba(28, 101, 148) -35.41%, #000 97.21%);
  background-size: contain
---

:apis-list{:persistPageNumber="true"}
::

