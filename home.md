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
  src: 'https://github.com/jharmn/img-bucket/blob/main/images/travel.png?raw=true'
  position: right
  max-width: 45%
styles: |
  background: linear-gradient(336deg, rgba(255,255,255,1) 48%, rgba(155,202,232,1) 100%);
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
  background: no-repeat center url('https://raw.githubusercontent.com/jharmn/img-bucket/4080647556993838400a68877338b338b566900a/images/Plane%20divider.svg')
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
  src: 'https://github.com/jillztom/kongair/blob/main/assets/code-sample.svg?raw=true'
padding: 50px 20px
styles: |
  img {
    box-shadow: 0px 0px 89px rgba(0, 0, 0, 0.1);
    border-radius: 20px;
  }
---
#title
Kickstart development with [easy APIs]{style="font-weight: 700; color: #022841"}
#description
Our APIs are dead simple to use and support industry standard SLAs.

#actions
  ::k-button{ size="large" appearance="secondary" to="/apis" }
  <svg width="20px" height="20px">
  <image xlink:href="https://github.com/jillztom/kongair/blob/main/assets/TerminalWindow.svg?raw=true" />
  </svg>
  Try it for free
  ::
::

::page-section
---
padding: 50px 0
styles: |
  background: no-repeat top url('https://github.com/jillztom/kongair/blob/main/assets/PlaneBg.svg?raw=true'), linear-gradient(45deg, rgba(255,255,255,1) 20%, rgba(155,202,232,1) 100%);
  background-size: contain
---
:apis-list{:persistPageNumber="true"}
::