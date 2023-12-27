[[COMP32211]]

- the ultimate power saving option is to have parts of a system which are present but completely unpowered - this means that all dissipation, static and dynamic, can be completely avoided
- one of the main concerns is making sure that any signals that come from a powered-off domain are clamped to harmless values. Additionally, when switched off any registers/memory info is lost, so restoring context can be an issue

- modern day example: ARM big.LITTLE employs two code-compatible ARM cores - a high performance core and low performance core. The high performance core is only switched on when processing demands require it