# This plugin is a copy of [serverless-aws-alias](https://www.npmjs.com/package/serverless-aws-alias) 

**NEW**

* Added support for serverless framework ver.2, see [details here](https://github.com/serverless-heaven/serverless-aws-alias/pull/186)

# Serverless AWS alias plugin

**The plugin requires Serverless 2!**

This plugin enables use of AWS aliases on Lambda functions. The term alias must not
be mistaken as the stage. Aliases can be deployed to stages, e.g. if you work on
different VCS branches in the same service, you can deploy your branch to a
new alias. The alias deployment can contain a different set of functions (newly
added ones or removed ones) and does not impact any other deployed alias.
Aliases also can be used to provide a 'real' version promotion.

As soon as the service is deployed with the plugin activated, it will create
a default alias that is named equally to the stage. This is the master alias
for the stage.

Each alias creates a CloudFormation stack that is dependent on the stage stack.
This approach has multiple advantages including easy removal of any alias deployment,
protecting the aliased function versions, and many more.
