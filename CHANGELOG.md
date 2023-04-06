# Changelog

## [11.0.0](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/compare/v10.2.1...v11.0.0) (2023-04-06)


### ⚠ BREAKING CHANGES

* this module no longer attempts to change file ownership automatically
* `make-fetch-happen` is now compatible with the following semver range for node: `^14.17.0 || ^16.13.0 || >=18.0.0`
* this drops support for node10 and non-LTS versions of node12 and node14
* this module now only supports taking a plain JavaScript options object, not a figgy pudding config object.
* drops support for node v8, since it's EOL as of 2020-01-01
* cache uid and gid are inferred from the cache folder itself, not passed in as options.
* node@4 is no longer supported
* **license:** license changed from CC0 to ISC.
* **agent:** pac proxies are no longer supported.
* **retry:** Retry logic has changes.
* **cache:** opts.cache -> opts.cacheManager; opts.cacheMode -> opts.cache
* **fetch:** opts.cache accepts a Cache-like obj or a path. Requests are now retried.
* **api:** actual api implemented

### Features

* **agent:** add ca/cert/key support to auto-agent ([#15](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/15)) ([57585a7](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/57585a7cef11f9b651fe3d0d8821e05b31f1119b))
* **agent:** added opts.strictSSL and opts.localAddress ([c35015a](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/c35015acf4a58e40868d39090e1a899308fcfaf9))
* **agent:** better, keepalive-supporting, default http agents ([16277f6](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/16277f697fe689932b7eec30115c72465dc7d01d))
* **api:** initial implementation -- can make and cache requests ([7d55b49](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/7d55b49c58506ae32039973880fb114bc4b0f3ae))
* **BREAKING:** refactor cache handling to be more consistent ([731b348](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/731b3483b87fe33d09c169a7628d5c586102d9dc)), closes [#49](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/49)
* cacache@12, no need for uid/gid opts ([fdb956f](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/fdb956fc3194d576b59935e89dda2c3ef2b335b3))
* **cache:** add special headers when request was loaded straight from cache ([8a7dbd1](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/8a7dbd11d0259ed9bb4046ab82481042fde8714b))
* **cache:** add useful headers to inform users about cached data ([9bd7b00](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/9bd7b0081fb2444301a6b23c00ae4ce738767681))
* **cache:** allow configuring algorithms to be calculated on insertion ([bf4a0f2](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/bf4a0f23e36f32bb33d7267348ddf2b226ba3396))
* **cache:** cache now obeys Age and a variety of other things ([#13](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/13)) ([7b9652d](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/7b9652d6eeff291e577b32389c41ada2b01767a7))
* **cache:** export cache deletion functionality ([#40](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/40)) ([3da4250](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/3da425055e32568298829262d28d090f5f66211e))
* **fetch:** injectable cache, and retry support ([87b84bf](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/87b84bf363460d19eb5c4e612b05feb4a5626a5b))
* fixed test dep requires; added mockRequire function to mock tests properly ([95de7a1](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/95de7a171110907e30f41f489e4be983cd8184a5))
* **github:** added github actions with coveralls integration ([1913c1b](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/1913c1b51aaac6044b4dab65b3d19ec943a35f39))
* implement local dns cache ([#132](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/132)) ([25cae2e](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/25cae2ec00c1b0549b40d3d076ed4beacea25ceb))
* **integrity:** full Subresource Integrity support ([#10](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/10)) ([a590159](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/a590159dd5efbc2b6dc9b6d4226a8f2cf0312e9d)), closes [#7](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/7)
* **memoization:** only slurp stuff into memory if opts.memoize is not false ([0744adc](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/0744adc6e7bf6cc8ed1d674a15f8a60000edfc87))
* **onretry:** Add `options.onRetry` ([#48](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/48)) ([f90ccff](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/f90ccff7dde79db855b60e4404fcd65f9553af62)), closes [#21](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/21)
* **opts:** fetch.defaults() for default options ([522a65e](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/522a65e7d55f44684df13039d4456db840a4d2ee))
* postinstall for dependabot template-oss PR ([c293053](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/c2930534bcf65907c4968ba5600d41910862fba5))
* **promises:** refactor bluebird with native promises ([7482d54](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/7482d54de989781248dec9c0d959947fd67ed23a))
* **proxy:** Added opts.noProxy and NO_PROXY support ([f45c915](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/f45c91542bbed89af198580e476b403e37c9198d)), closes [#17](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/17)
* refactored functions into utilities ([74620dd](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/74620dd7c2262ac46d9b4f6ac2dc9ff45a4f19ee))
* **retry:** accept shorthand retry settings ([dfed69d](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/dfed69d7eddadb8a4e6cbf829cfef42c6cd4b907))
* **retry:** report retry attempt number as extra header ([fd50927](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/fd5092775af834c4bdbdaecfbda5636570f958be))
* **retry:** retry requests on 408 timeouts, too ([8d8b5bd](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/8d8b5bd48d93eb94ce97227baa5d589b74190417))
* store link header ([#164](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/164)) ([dae6384](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/dae6384a7f20c541708804b08ce233d14d592613))
* **streams:** refactor node streams with minipass ([1d7f5a3](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/1d7f5a3f79dda02b87885ed4e0983b96149dd2c1))
* updated dev deps; update tap; updated standard ([dce6eec](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/dce6eece130fb20164a62eeabc6090811d8f14a4))
* updated fetch module; linting mostly; based on testing ([063f28e](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/063f28ea1ac23f7e9d9d79e15949ca82b634ce97))
* updated fetch tests; linting, logic, added tests ([d50aeaf](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/d50aeafebeb5d8f7118d7f6660208f40ac487804))
* use globalAgent when in lambda ([bd9409d](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/bd9409da246a979b665ebd23967ec01dd928ce47)), closes [#4](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/4)
* **utils:** fixed configure-options based on testing ([9dd4f6f](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/9dd4f6f108442dc247de44e1ddc0341edcb84c9b))


### Bug Fixes

* add code property to unsupported proxy url error ([#112](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/112)) ([569a613](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/569a6136b0ded34edd5de3584f518233fc720fcd))
* Add year to license ([#68](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/68)) ([d0d86eb](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/d0d86eb42fa16b7d5de51d77c69255efb437daf6))
* added tests to ensure username and password are url-decoded ([cabacdc](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/cabacdc0e0d6d7e701f98c8b51136bd16ada84be))
* address data corruption when cache is slow ([7f896be](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/7f896bef4bbcab73eccb92b5999204b673cdf485))
* **agent:** {agent: false} has special behavior ([b8cc923](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/b8cc923c4f9076ce5404c8c190878a5e8b7d5615))
* **agent:** accept Request as fetch input, not just strings ([b71669a](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/b71669a46a96e9138010bb050592adaaca72369f))
* **agent:** check uppercase & lowercase proxy env ([#24](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/24)) ([acf2326](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/acf2326c8a341df20539abab8ac25a5b38ae16e7)), closes [#22](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/22)
* **agent:** don't use polynomial regex ([61856c6](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/61856c65149f74ab353d8d6d401e90abb6f30950))
* **agent:** nudge around things with opts.agent ([ed62b57](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/ed62b57922ac653803abbc86efea5ede411f25d3))
* **agent:** support timeout durations greater than 30 seconds ([04875ae](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/04875aecb6bdd55804a98cbcfd47f249e8605db0))
* cache integrity and size events so late listeners still get them ([#154](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/154)) ([8c78584](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/8c7858490aa5dc40e13d1c2580b5937836111a5b))
* **cache:** bump cacache for its fixed error messages ([2f2b916](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/2f2b916aa01f672f67bd1706e9a304040f2f2c4d))
* **cache:** default on cache-control header ([b872a2c](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/b872a2c04492a1dba973c604916c64542602fea5))
* **cache:** encode x-local-cache-etc headers to be header-safe ([dc9fb1b](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/dc9fb1bd69d6f3705964e146ee093ecd339696e1))
* **cache:** fix handling of errors in cache reads ([5729222](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/5729222a89467f08e44d6c421997baf529f1b1c7))
* **cache:** if metadata is missing for some odd reason, ignore the entry ([a021a6b](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/a021a6b894133a2a7fefd7c623781933b92a1a14))
* **cache:** invalidation on non-GET ([fe78fac](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/fe78face92e2c7dd4c3c3ce4cd3bbbebe3eca0da))
* **cache:** make force-cache and only-if-cached work as expected ([f50e9df](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/f50e9dfebd06e1f1fe165b048c34af1c474b7079))
* **cache:** more spec compliance ([d5a56db](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/d5a56dbf48a183fc553f27cc77ca9637f709d4db))
* **cache:** only cache 200 gets ([0abb25a](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/0abb25a893de4846cb589932d7c123d1cb04fdff))
* **cache:** only load cache code if cache opt is a string ([250fcd5](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/250fcd522229faa31c6b58d539ff1ab4710efb27))
* **cache:** oops ([e3fa15a](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/e3fa15aaa38abb0e696a721c37ba934f145e66d2))
* **cache:** pass uid/gid/Promise through to cache ([a847c92](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/a847c9249cdf5701d01317db087bb07e2a4d3d23))
* **cache:** pretend cache entry is missing on ENOENT ([9c2bb26](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/9c2bb26a2942862ff93c493a6caf4a7a51dd6859))
* **cache:** reduce race condition window by checking for content ([24544b1](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/24544b15e217593cff48cca57b3a7d8a956cb7c8))
* **cache:** refactored warning removal into main file ([5b0a9f9](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/5b0a9f9e1747a2c1f7580fdb8acbaaf01b30d938))
* **cache:** req constructor no longer needed in Cache ([5b74cbc](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/5b74cbcd8827c7cc6a229e01a71f579e796c38cd))
* **cache:** standard fetch api calls cacheMode "cache" ([6fba805](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/6fba805572eba3e29aad6c1c44caf41a786b83d3))
* **cache:** stop relying on BB.catch ([2b04494](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/2b04494693116e33f934574df0f6ba9b7a79d84f))
* **cache:** treat caches as private ([57b7dc2](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/57b7dc20f499b8c289aabd7705e695ad13805706))
* **cache:** use the passed-in promise for resolving cache stuff ([4c46257](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/4c4625716f21420c7b44f3f7e2c2f282cd3a6758))
* **cache:** was using wrong method for non-GET/HEAD cache invalidation ([810763a](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/810763a485b1a6bdd82a75ecadd4bb04aca35f01))
* **caching:** a bunch of cache-related fixes ([8ebda1d](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/8ebda1d7557ad315f582fb2a222277aa9c925872))
* compress option and accept/content encoding header edge cases ([#65](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/65)) ([f7d1255](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/f7d1255951f936713a260efc85d4727f2b05eafe))
* default verbatim to undefined ([#135](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/135)) ([be0cf6a](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/be0cf6a15949c0511b40ed086aeab29fb86c2259))
* **deps:** `cacache@6.3.0` - race condition fixes ([9528442](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/9528442cdfaac94893556e5de25045d12346c205))
* **deps:** bump cacache and use its size feature ([926c1d3](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/926c1d3c54f2de0b267b7c50d103fe2ed5036ee1))
* **deps:** bump dep versions with bugfixes ([0af4003](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/0af40039bf348714c0a7823fd634d6dfe7b816c2))
* **deps:** bump deps with ssri fix ([bef1994](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/bef1994a656fd79c85e290b405967ead65c6ff6f))
* **deps:** bump other deps for bugfixes ([eab8297](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/eab82974c699b321855dcf57fb20ce7042cbfbaf))
* **deps:** make sure node-fetch tarball included in release ([3bf49d1](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/3bf49d165f50047f8eb5e44d2c7668ebb299d7f8))
* **deps:** manually pull in newer node-fetch to avoid babel prod dep ([66e5e87](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/66e5e872435a30cdb7785e1294d82478630d915a))
* **deps:** move test-only deps to devDeps ([2daaf80](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/2daaf807fd40157474f0785b87468a3b0f3b3bd8))
* **deps:** pull in various fixes from deps ([fc2a587](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/fc2a58795d127eb6ff8264941426018f117a310a))
* **deps:** seriously ([c29e7e7](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/c29e7e7aebbcaf16846215e94d83e593a6aebd8d))
* **deps:** switch to node-fetch-npm and stop bundling ([3db603b](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/3db603b2293d5c23500922aaeb9a1e27b699ff49))
* **deps:** use bundleDeps instead ([c36ebf0](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/c36ebf0ad241fe31b282d667b9bafdcbd842fa8b))
* **docs:** remove reference to unsupported feature ([#153](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/153)) ([1d454f1](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/1d454f11877267e1f80a9cc42f8f249fe6ec887f)), closes [#147](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/147)
* **docs:** this module uses minipass-fetch, not node-fetch ([bc77a29](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/bc77a29d40eb98b8d1e496b0500e217cf7591b68))
* force negotiator to preload all modules ([#50](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/50)) ([2c22690](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/2c22690c1e2b79ee8be3d133b944104c8c595f50))
* format cache key with new URL object shape ([21cb6cc](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/21cb6cc968aabff8b5c5c02e3666fb093fd6578c))
* **freshness:** fix regex for cacheControl matching ([070db86](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/070db861eac2a17386686147fa2c72e7f6e9a849))
* **freshness:** fixed default freshness heuristic value ([5d29e88](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/5d29e8800ec999d5a092c0991155d4f41e2b1341))
* implement cache modes correctly ([cd80a26](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/cd80a267337a812574e1ce896b332f68d8164d3d)), closes [#52](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/52)
* **integrity:** disable node-fetch compress when checking integrity ([#42](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/42)) ([a7cc74c](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/a7cc74c3e25fb1f7bde44318b8add45af66696e4))
* **integrity:** hash verification issues fixed ([07f9402](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/07f9402969d1f346d93cbd3a73e1494a4bdf4c40))
* **integrity:** update cacache and ssri and change EBADCHECKSUM -&gt; EINTEGRITY ([b6cf6f6](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/b6cf6f669cae65578e144251afaa95ee5276ead9))
* **integrity:** use new sri.match() for verification ([4f371a0](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/4f371a05972ad7c4bbd34a23557d4135be74c870))
* Keep exports the same as `node-fetch` ([4f33847](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/4f3384738fe02a993b0e9f94f182ea5831975bf7)), closes [#23](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/23)
* **license:** switch to ISC ([#49](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/49)) ([bf90c6d](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/bf90c6dca6f0dc66599e60ffe01e5afcb6cde08d))
* linting ([#166](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/166)) ([e9a2a51](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/e9a2a51e6d72e75802a73fe3b2b0e84753cc202a))
* **logging:** remove console.log calls ([a1d0a47](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/a1d0a47467c8657a6618f6e1cf444e21f31e0859))
* make `defaults` chaining actually work ([#144](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/144)) ([aa71e81](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/aa71e817c71968f547f4d1756b1faf92db7b79ec))
* **match:** Rewrite the conditional stream logic ([#25](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/25)) ([66bba4b](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/66bba4ba0c3a5aadb2e26225ba3b8d53d88728e4))
* **memoization:** missed spots + allow passthrough of memo objs ([ac0cd12](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/ac0cd123026e579ff041200f2583b57920e777db))
* **memoize:** cacache had a broken memoizer ([8a9ed4c](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/8a9ed4caa89f3ad754264693a2f77d0bea6463cd))
* **method:** node-fetch guarantees uppercase ([a1d68d6](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/a1d68d6d478ef8d277cfd3f10bb45ffd437c4549))
* move to template-oss ([105872f](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/105872f6fede073c1423d8b7548afdfcad06b89a))
* **opts:** simplified opts handling ([516fd6e](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/516fd6e7ac0de04a2ab794238114e97906987e49))
* pass expected integrity to cacache ([a88213e](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/a88213e6a5e3a74c746d326488e2e6e056a2df54))
* pass integrityEmitter to cacache to avoid a redundant integrity stream ([ae62c21](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/ae62c21c70d2004bbaa967ae2b722890b4283cbb))
* polish out an unnecessary URL object creation ([67a01d4](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/67a01d46b2cacbadc22f49604ee524526cee3912)), closes [#14](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/14)
* preserve rfc7234 5.5.4 warnings ([001b91e](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/001b91ee7d4411874b131e9a8531e3a0d00df999))
* properly detect thrown HTTP "error" objects ([d7cbeb4](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/d7cbeb4d6205d8f31c57de50bb88d583ba0e9c1f))
* **proxy:** bump proxy deps with bugfixes ([#32](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/32)) ([632f860](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/632f860ab78a3b4d662dc6070576b24c22ee0d98))
* **proxy:** choose agent for http(s)-proxy by protocol of destUrl ([ea4832a](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/ea4832acdc669ae5f58a6eb3837952969c4d9b56))
* **proxy:** make socks proxy working ([1de810a](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/1de810ab5452915dc8b6329df1e7e3010f094473))
* **proxy:** pass proxy option directly to ProxyAgent ([3398460](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/339846034f856daa865ec25e1fc92e1f27fddc48))
* **proxy:** revert previous proxy solution ([563b0d8](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/563b0d840e9999c07193bc7cdd952ab2aa881d39))
* **proxy:** use auth parameter for proxy authentication ([#30](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/30)) ([c687306](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/c687306af354d09304dcc71ec1769dbde16c971c))
* **proxy:** use the destination url when determining agent ([1a714e7](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/1a714e7b77b9d006f24dbde806ec1c5d9d177c35))
* **redirect:** handle redirects explicitly  ([#27](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/27)) ([4c4af54](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/4c4af5451ecfe409b2f912d8d9bd4c0b472bceed))
* **redirect:** redirects now delete authorization if hosts fail to match ([c071805](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/c071805f8d927c2401bb2388e87ceddd82fe6d76))
* remoteFetch takes instance of fetch.Headers ([6e0de7b](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/6e0de7b10b8597eaff69fea06a266914766cf5ab)), closes [#22](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/22)
* remove in-memory buffering in favor of full time streaming ([ec2db21](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/ec2db214e4d54a8ba81a4315b4b3f21e71181069))
* respect given algorithms instead of always using sha512 ([#156](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/156)) ([9baa806](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/9baa8065f32a89ebd49eb59258462c209a68f142))
* retry ERR_SOCKET_TIMEOUT from agentkeepalive ([#54](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/54)) ([7b55d54](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/7b55d5438ec916ae36e51f0c6611c21a7e37a454))
* **retry:** be more specific about when we retry ([a47b782](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/a47b782c0c20d872821b9cbe3c119965e201e9e0))
* **retry:** false -&gt; {retries: 0} ([297fbb6](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/297fbb600ab1a9c0d2d809164bae29f46afb896f))
* **retry:** only retry put if body is not a stream ([a24e599](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/a24e599ee167ffc2fa2c5eed7d1f14987e1b99a5))
* **retry:** skip retries if body is a stream for ANY method ([780c0f8](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/780c0f841cc47a48af5ec5285d1e03afb17e3043))
* **retry:** stop retrying 404s ([6fafd53](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/6fafd5306b1addb33e8719c771a42a14660d397c))
* revert negotiator preload hack ([8688f09](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/8688f0952cb5710f6e802ae2858d6f00efc2d71d))
* safely create synthetic response body for 304 ([bc70f88](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/bc70f884143c47128ed0d1e5c375af1c1160a0fa))
* set agentkeepalive freeSocketTimeout back to 15 seconds ([#100](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/100)) ([3371abf](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/3371abf9e342d75bdc063b346bdefedd573f55a9))
* skip integrity check on error ([4cffbe0](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/4cffbe0aa07300805be3fc09d0413f25356c01bc)), closes [#29](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/29)
* **staleness:** responses older than 8h were never stale :&lt; ([b54dd75](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/b54dd758fd9e6c9265c72a51855657185ed3206f))
* standard stuff and cache matching ([753f2c2](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/753f2c2dbf03a709d559211ec12594134457f817))
* **standard:** standard@11 update ([ff0aa70](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/ff0aa70aa24e44e057ff1747e95f36d667db179b))
* store a timestamp in the metadata instead of relying on the entry ([#57](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/57)) ([27f357f](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/27f357f7a74c2a886b32defcd9f6eef4d0a22bfe)), closes [#55](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/55)
* **streams:** change condition/logic of fitInMemory used when defining memoize ([c173723](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/c173723bdaef34c8f9ccf46b6a5c5de0610bd944))
* strip cookie header on redirect across hostnames ([#71](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/71)) ([ec53f27](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/ec53f27335a8d1b981c7d32e941e71e4d2851efb))
* support url-encoded proxy authorization ([cabacdc](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/cabacdc0e0d6d7e701f98c8b51136bd16ada84be)), closes [#47](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/47)
* support user without password in proxy auth ([e24bbf9](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/e24bbf935bc8a2c49070cdb2518e5ee290143191))
* TypeError: SocksProxyAgent is not a constructor ([#161](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/161)) ([4ae4864](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/4ae48640b091f4f64ad4c52037c147b1dfd83f04))
* Update inline license to use [@license](https://github.com/license) comment ([#67](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/67)) ([f602e06](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/f602e0644c435f7f68b5c17b1b275ad0829b260f))
* updated 'files' property in package file ([945e40c](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/945e40c7fbb59333e0c632c490683e4babc68dc1))
* use hostname for socks agent ([#159](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/159)) ([331f9cb](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/331f9cb273584da452994c6d9ce3e36df2bafb03))
* use the same strictSSL default as tls.connect ([4d7b9c7](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/4d7b9c7e9f243258bff8329eba0beae448304af8))
* Use WhatWG URL objects over deprecated legacy url API ([28aca97](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/28aca97dfb63ca003ebf62d1b961771cfbb2481d))
* **warning:** remove spurious warning, make format more spec-compliant ([2e4f6bb](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/2e4f6bbb53c7d02b0e855a610efa3cb34f7c5712))
* when encountering errors reading content, clean up after ourselves ([#56](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/56)) ([d05704f](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/d05704ff77e602cc1bbc1370623e714ba4faeb3f))


### meta

* drop node@4, add node@9 ([7b0191a](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/7b0191a4a36925e0e33cc0a00fbf2778af383fb1))


* drop node 8 ([9fa7944](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/9fa7944cbc603f3a194dfb440f519a7d5265653e))
* update cacache and ssri ([09e4f97](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/09e4f9794a6f134d3f1d8e65eb9bd940e38e5bfc))


### Documentation

* add a bit more detail to readme contributin section ([11774a1](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/11774a12aff370ffc66abd686ae0fd5804810d79))
* changelog for v9.0.0 and v9.0.3 ([4ea64da](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/4ea64da90ee1116ab71fd5d1e76734a500ea676e))
* clarify node-fetch-npm vs node-fetch usage ([#45](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/45)) ([cf28f83](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/cf28f837402274cd423af35dd29c23e80235860b))
* clarify project purpose a bit ([#20](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/20)) ([781d367](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/781d367e2523502edb4085f8e3b9d09fd4805304))
* **coc:** updated CODE_OF_CONDUCT.md ([75586b1](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/75586b155142c9e9c26b3d31e2f16737575265d2))
* **coc:** updated CODE_OF_CONDUCT.md ([5ad322c](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/5ad322cb5f632c9c1aa9e4d540ae796b036c44d1))
* **contributing:** updated CONTRIBUTING.md ([5a6fa7f](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/5a6fa7f5fdb9283dab70b1811f2a23a99f83951e))
* document cause argument to onRetry ([#173](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/173)) ([d63de44](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/d63de4427ecadcc1c5a688564df8449ca182aafd))
* document old feature of interest ([cb5d1c6](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/cb5d1c6bdd673b7a1d663d3e1052ce7cd4379442))
* filled out readme ([38baef4](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/38baef4fbb73d07701bde8367ff9e73ba1a89a22))
* fix contributing section ([d384669](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/d3846697ff502dd957284cba3c725b39595dc805))
* mention RFC7234 section for freshness lifetime ([d4aa9ea](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/d4aa9ea7bb7126b306b40455b1f1de330964dc32))
* oops, this was already implemented ([cb87be6](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/cb87be67eb3558cee645b66d90f17cae20307fb2))
* remove mention of custom cache provider ([#136](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/136)) ([a7f1b55](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/a7f1b554bc0072a1545d96f316e252ec52e81b23))
* update readme after recent changes ([5f59309](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/5f593099a079ff460cd659cf67be8e55573ba3dc))
* updated README; fixed url links ([c9a17e8](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/c9a17e8f1b7f703d61e93a3f6819fbde699760a8))


### Dependencies

* `standard@10.0.1` ([36cdc1c](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/36cdc1c7b581da64e66f88e84b42185fa77287e9))
* added require-inject to devDeps ([be0eb77](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/be0eb77c2b41253eafb6920abf008b14110aec49))
* bump cacache from 15.3.0 to 16.0.0 ([#121](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/121)) ([de032e9](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/de032e9018c459ee7acd76448ed198040beb3418))
* bump cacache from 16.1.3 to 17.0.0 ([#184](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/184)) ([33d972a](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/33d972a81517c6817b39dd9c8adf9bfa7cf78391))
* bump deps ([39c3339](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/39c33390c7664b567726e549ec1d7f2e2648737a))
* bump deps ([62e91e2](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/62e91e2afc3a2649998eb037501eb47ac2e69dc8))
* bump deps ([48cb398](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/48cb3982d81467e816ef44d4e3becbfb08b81762))
* bump deps ([0c3a312](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/0c3a3124d132e732f6ef055efffed51eb806d86f))
* bump devdeps ([3cc1d43](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/3cc1d43e76e97d4abc4901481fb973d35bdd304d))
* bump devDeps ([ba4e110](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/ba4e110f6f17dd7d73131925b7eaf5cb2accac49))
* bump devDeps ([5b6bc88](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/5b6bc88c81ef41c18eadb270b13e53ddc9774f69))
* bump lru-cache from 6.0.0 to 7.0.1 ([3e353d2](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/3e353d2bf7ce035346295eb5ffd5c2d169466537))
* bump lru-cache from 7.18.3 to 8.0.5 ([08c8abd](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/08c8abd1e5dc637cd6225e7ac772312b6f7a8290))
* bump minipass from 3.3.6 to 4.0.0 ([77018ff](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/77018ff5c7ceeeda92e7d62435c4a6214e966a99))
* bump minipass-fetch from 1.4.1 to 2.0.1 ([#108](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/108)) ([0257b63](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/0257b637dde5831c9a9f1f652282d7818bebfa4a))
* bump minipass-fetch from 2.1.2 to 3.0.0 ([ebd86b2](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/ebd86b27813fde64cdeb1997857735dba7a25f85))
* bump npmlog ([cb8c2a6](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/cb8c2a61e485b36779a81940d5ebcdd1454e889b))
* bump nyc ([64a21f0](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/64a21f089a63f96165422aa77474b47102bc2a06))
* bump socks-proxy-agent from 6.2.1 to 7.0.0 ([#158](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/158)) ([63ed403](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/63ed40395ea2c34313575b42e083a428b506fd88))
* bump ssri from 8.0.1 to 9.0.0 ([#139](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/139)) ([f91a1cc](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/f91a1ccd0ea2821a3686b4b8ffd3fad47c2aeabd))
* bump ssri from 9.0.1 to 10.0.0 ([9c16d84](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/9c16d84c10dddada3a1d0aeb74ad7b77220dd7eb))
* bumping and regenerating package-lock.json ([c362e1d](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/c362e1ddf07acc3977c703f1eeeefe0a9a746130))
* http-cache-semantics@4.1.1 ([#210](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/210)) ([5807162](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/58071621daa6d7e1cb28a61fc06df531baf440f3))
* http-proxy-agent@5.0.0 ([0013272](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/00132720316b4ed5df66240fe0860f914378addf))
* https-proxy-agent@2.2.3 ([2141605](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/21416051f1f100cd7993af418f2e4da922d24a24))
* https-proxy-agent@3.0.1 ([a8b0ef0](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/a8b0ef0b7b826ebcffc902d4ef64dae9de820a11))
* lru-cache@5.1.1 ([292288e](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/292288e1c68eebd6d9f6b909f4e357a4389dbe8d))
* negotiator@0.6.3 ([70d3496](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/70d3496dbf5badb1fae60fb6bf454313ee6d4648))
* npmlog@6.0.0 ([09ebad1](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/09ebad1c3394ca430a0b65848e9169df1872a35c))
* remove unused dependencies ([#212](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/212)) ([fb01043](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/fb0104335a2101e4f21721457e80b59a8300017e))
* tap@12.7.0 ([d252843](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/d252843959af74dbeb7b7782cae3e94bcc8a52e5))
* update agentkeepalive requirement from ^4.1.3 to ^4.2.0 ([ed7f983](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/ed7f98364f9a5b11c8fc5fd088c68d04df42415d))
* update agentkeepalive requirement from ^4.2.0 to ^4.2.1 ([#102](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/102)) ([0252efc](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/0252efcb934c2b3d95af366d79b26d74aa477ca9))
* update cacache requirement from ^15.2.0 to ^15.3.0 ([46e0ac4](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/46e0ac4f54a2cdf4ec925768238073ac941ed8d9))
* update cacache requirement from ^16.0.0 to ^16.0.1 ([#122](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/122)) ([cb3873c](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/cb3873cbe774e182d954c601af35c022783a5d5c))
* update cacache requirement from ^16.0.1 to ^16.0.2 ([#127](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/127)) ([44fe6ce](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/44fe6ce8c9326b181913564e4808fce7df6f589b))
* update everything to use latest minipass ([f89d3e1](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/f89d3e1ae50d8371dce650dcf0091ce68bf7adb7))
* update lru-cache requirement from ^7.0.1 to ^7.3.0 ([e825c2c](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/e825c2c26d41fe9076031c62827c5dc91898837e))
* update lru-cache requirement from ^7.3.0 to ^7.3.1 ([6ca02ad](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/6ca02ad504a7eaf62e81cf170cd5e947ef79584d))
* update lru-cache requirement from ^7.3.1 to ^7.4.0 ([#103](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/103)) ([140ff64](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/140ff64e90962ba5b8f7be7ef39446a669cfe572))
* update lru-cache requirement from ^7.4.0 to ^7.4.1 ([#113](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/113)) ([b7f3e28](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/b7f3e28f07c0e023dc6b616f61957fc49b3fdd2c))
* update lru-cache requirement from ^7.4.1 to ^7.4.2 ([#115](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/115)) ([a3f4ba9](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/a3f4ba975247f31a803be9afd95fc652e4043cc6))
* update lru-cache requirement from ^7.4.2 to ^7.4.4 ([#117](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/117)) ([24a7ddd](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/24a7ddd3a6970cc9b0d92807c9db002fcb53a913))
* update lru-cache requirement from ^7.4.4 to ^7.5.0 ([#119](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/119)) ([5ef3bb3](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/5ef3bb38b4fd122d5ffc012420e94a623a3d300d))
* update lru-cache requirement from ^7.5.0 to ^7.5.1 ([#120](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/120)) ([8c5db07](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/8c5db07f31f422de646026d7fb437bc4a6233473))
* update lru-cache requirement from ^7.5.1 to ^7.7.1 ([#128](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/128)) ([eb6e7b6](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/eb6e7b657d0b9da6d1063d2ff3d9f08b3827c017))
* update minipass requirement from ^3.1.3 to ^3.1.6 ([778c46a](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/778c46a42e0e674d61bcce38cb248263c5a1149f))
* update minipass-fetch requirement from ^1.3.2 to ^1.4.1 ([6fabf4c](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/6fabf4c23c8a33dce221ea2fac8cb1ecd14767a1))
* update minipass-fetch requirement from ^2.0.1 to ^2.0.2 ([#109](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/109)) ([4a9892a](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/4a9892a0fbf79965ed272d9bc5422c4525e7a990))
* update minipass-fetch requirement from ^2.0.2 to ^2.0.3 ([#114](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/issues/114)) ([bc71014](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/bc71014c485a6963d8b6f5d8a3af793465bf9b39))
* update socks-proxy-agent requirement from ^6.0.0 to ^6.1.1 ([58f3b29](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/58f3b291eaec6bd6ce534de51ee8db9dd8348e4a))
* update ssri requirement from ^8.0.0 to ^8.0.1 ([5b75b08](https://github.com/samkenxstream/SAMkenxmake-fetch-happen/commit/5b75b089a66c9c26564034d55dc0d04f5f59a515))

## [11.0.3](https://github.com/npm/make-fetch-happen/compare/v11.0.2...v11.0.3) (2023-02-02)

### Dependencies

* [`fb01043`](https://github.com/npm/make-fetch-happen/commit/fb0104335a2101e4f21721457e80b59a8300017e) [#212](https://github.com/npm/make-fetch-happen/pull/212) remove unused dependencies (#212)
* [`5807162`](https://github.com/npm/make-fetch-happen/commit/58071621daa6d7e1cb28a61fc06df531baf440f3) [#210](https://github.com/npm/make-fetch-happen/pull/210) `http-cache-semantics@4.1.1` (#210)

## [11.0.2](https://github.com/npm/make-fetch-happen/compare/v11.0.1...v11.0.2) (2022-12-07)

### Dependencies

* [`77018ff`](https://github.com/npm/make-fetch-happen/commit/77018ff5c7ceeeda92e7d62435c4a6214e966a99) [#194](https://github.com/npm/make-fetch-happen/pull/194) bump minipass from 3.3.6 to 4.0.0

## [11.0.1](https://github.com/npm/make-fetch-happen/compare/v11.0.0...v11.0.1) (2022-10-17)

### Dependencies

* [`ebd86b2`](https://github.com/npm/make-fetch-happen/commit/ebd86b27813fde64cdeb1997857735dba7a25f85) [#186](https://github.com/npm/make-fetch-happen/pull/186) bump minipass-fetch from 2.1.2 to 3.0.0
* [`9c16d84`](https://github.com/npm/make-fetch-happen/commit/9c16d84c10dddada3a1d0aeb74ad7b77220dd7eb) [#187](https://github.com/npm/make-fetch-happen/pull/187) bump ssri from 9.0.1 to 10.0.0

## [11.0.0](https://github.com/npm/make-fetch-happen/compare/v10.2.1...v11.0.0) (2022-10-13)

### ⚠️ BREAKING CHANGES

* this module no longer attempts to change file ownership automatically
* `make-fetch-happen` is now compatible with the following semver range for node: `^14.17.0 || ^16.13.0 || >=18.0.0`

### Features

* [`c293053`](https://github.com/npm/make-fetch-happen/commit/c2930534bcf65907c4968ba5600d41910862fba5) [#177](https://github.com/npm/make-fetch-happen/pull/177) postinstall for dependabot template-oss PR (@lukekarrys)

### Documentation

* [`d63de44`](https://github.com/npm/make-fetch-happen/commit/d63de4427ecadcc1c5a688564df8449ca182aafd) [#173](https://github.com/npm/make-fetch-happen/pull/173) document cause argument to onRetry (#173) (@jmpage)

### Dependencies

* [`33d972a`](https://github.com/npm/make-fetch-happen/commit/33d972a81517c6817b39dd9c8adf9bfa7cf78391) [#184](https://github.com/npm/make-fetch-happen/pull/184) bump cacache from 16.1.3 to 17.0.0 (#184)

## [10.2.1](https://github.com/npm/make-fetch-happen/compare/v10.2.0...v10.2.1) (2022-08-15)


### Bug Fixes

* linting ([#166](https://github.com/npm/make-fetch-happen/issues/166)) ([e9a2a51](https://github.com/npm/make-fetch-happen/commit/e9a2a51e6d72e75802a73fe3b2b0e84753cc202a))

## [10.2.0](https://github.com/npm/make-fetch-happen/compare/v10.1.8...v10.2.0) (2022-07-19)


### Features

* store link header ([#164](https://github.com/npm/make-fetch-happen/issues/164)) ([dae6384](https://github.com/npm/make-fetch-happen/commit/dae6384a7f20c541708804b08ce233d14d592613))

## [10.1.8](https://github.com/npm/make-fetch-happen/compare/v10.1.7...v10.1.8) (2022-06-20)


### Bug Fixes

* TypeError: SocksProxyAgent is not a constructor ([#161](https://github.com/npm/make-fetch-happen/issues/161)) ([4ae4864](https://github.com/npm/make-fetch-happen/commit/4ae48640b091f4f64ad4c52037c147b1dfd83f04))

### [10.1.7](https://github.com/npm/make-fetch-happen/compare/v10.1.6...v10.1.7) (2022-06-01)


### Bug Fixes

* use hostname for socks agent ([#159](https://github.com/npm/make-fetch-happen/issues/159)) ([331f9cb](https://github.com/npm/make-fetch-happen/commit/331f9cb273584da452994c6d9ce3e36df2bafb03))


### Dependencies

* bump socks-proxy-agent from 6.2.1 to 7.0.0 ([#158](https://github.com/npm/make-fetch-happen/issues/158)) ([63ed403](https://github.com/npm/make-fetch-happen/commit/63ed40395ea2c34313575b42e083a428b506fd88))

### [10.1.6](https://github.com/npm/make-fetch-happen/compare/v10.1.5...v10.1.6) (2022-05-27)


### Bug Fixes

* respect given algorithms instead of always using sha512 ([#156](https://github.com/npm/make-fetch-happen/issues/156)) ([9baa806](https://github.com/npm/make-fetch-happen/commit/9baa8065f32a89ebd49eb59258462c209a68f142))

### [10.1.5](https://github.com/npm/make-fetch-happen/compare/v10.1.4...v10.1.5) (2022-05-19)


### Bug Fixes

* cache integrity and size events so late listeners still get them ([#154](https://github.com/npm/make-fetch-happen/issues/154)) ([8c78584](https://github.com/npm/make-fetch-happen/commit/8c7858490aa5dc40e13d1c2580b5937836111a5b))

### [10.1.4](https://github.com/npm/make-fetch-happen/compare/v10.1.3...v10.1.4) (2022-05-18)


### Bug Fixes

* **docs:** remove reference to unsupported feature ([#153](https://github.com/npm/make-fetch-happen/issues/153)) ([1d454f1](https://github.com/npm/make-fetch-happen/commit/1d454f11877267e1f80a9cc42f8f249fe6ec887f)), closes [#147](https://github.com/npm/make-fetch-happen/issues/147)
* pass expected integrity to cacache ([a88213e](https://github.com/npm/make-fetch-happen/commit/a88213e6a5e3a74c746d326488e2e6e056a2df54))
* pass integrityEmitter to cacache to avoid a redundant integrity stream ([ae62c21](https://github.com/npm/make-fetch-happen/commit/ae62c21c70d2004bbaa967ae2b722890b4283cbb))
* remove in-memory buffering in favor of full time streaming ([ec2db21](https://github.com/npm/make-fetch-happen/commit/ec2db214e4d54a8ba81a4315b4b3f21e71181069))

### [10.1.3](https://github.com/npm/make-fetch-happen/compare/v10.1.2...v10.1.3) (2022-05-09)


### Bug Fixes

* make `defaults` chaining actually work ([#144](https://github.com/npm/make-fetch-happen/issues/144)) ([aa71e81](https://github.com/npm/make-fetch-happen/commit/aa71e817c71968f547f4d1756b1faf92db7b79ec))

### [10.1.2](https://github.com/npm/make-fetch-happen/compare/v10.1.1...v10.1.2) (2022-04-05)


### Dependencies

* bump ssri from 8.0.1 to 9.0.0 ([#139](https://github.com/npm/make-fetch-happen/issues/139)) ([f91a1cc](https://github.com/npm/make-fetch-happen/commit/f91a1ccd0ea2821a3686b4b8ffd3fad47c2aeabd))

### [10.1.1](https://github.com/npm/make-fetch-happen/compare/v10.1.0...v10.1.1) (2022-03-29)


### Bug Fixes

* default verbatim to undefined ([#135](https://github.com/npm/make-fetch-happen/issues/135)) ([be0cf6a](https://github.com/npm/make-fetch-happen/commit/be0cf6a15949c0511b40ed086aeab29fb86c2259))


### Documentation

* remove mention of custom cache provider ([#136](https://github.com/npm/make-fetch-happen/issues/136)) ([a7f1b55](https://github.com/npm/make-fetch-happen/commit/a7f1b554bc0072a1545d96f316e252ec52e81b23))

## [10.1.0](https://github.com/npm/make-fetch-happen/compare/v10.0.6...v10.1.0) (2022-03-24)


### Features

* implement local dns cache ([#132](https://github.com/npm/make-fetch-happen/issues/132)) ([25cae2e](https://github.com/npm/make-fetch-happen/commit/25cae2ec00c1b0549b40d3d076ed4beacea25ceb))


### Dependencies

* update cacache requirement from ^16.0.0 to ^16.0.1 ([#122](https://github.com/npm/make-fetch-happen/issues/122)) ([cb3873c](https://github.com/npm/make-fetch-happen/commit/cb3873cbe774e182d954c601af35c022783a5d5c))
* update cacache requirement from ^16.0.1 to ^16.0.2 ([#127](https://github.com/npm/make-fetch-happen/issues/127)) ([44fe6ce](https://github.com/npm/make-fetch-happen/commit/44fe6ce8c9326b181913564e4808fce7df6f589b))
* update lru-cache requirement from ^7.5.1 to ^7.7.1 ([#128](https://github.com/npm/make-fetch-happen/issues/128)) ([eb6e7b6](https://github.com/npm/make-fetch-happen/commit/eb6e7b657d0b9da6d1063d2ff3d9f08b3827c017))

### [10.0.6](https://www.github.com/npm/make-fetch-happen/compare/v10.0.5...v10.0.6) (2022-03-14)


### Dependencies

* bump cacache from 15.3.0 to 16.0.0 ([#121](https://www.github.com/npm/make-fetch-happen/issues/121)) ([de032e9](https://www.github.com/npm/make-fetch-happen/commit/de032e9018c459ee7acd76448ed198040beb3418))
* update lru-cache requirement from ^7.4.1 to ^7.4.2 ([#115](https://www.github.com/npm/make-fetch-happen/issues/115)) ([a3f4ba9](https://www.github.com/npm/make-fetch-happen/commit/a3f4ba975247f31a803be9afd95fc652e4043cc6))
* update lru-cache requirement from ^7.4.2 to ^7.4.4 ([#117](https://www.github.com/npm/make-fetch-happen/issues/117)) ([24a7ddd](https://www.github.com/npm/make-fetch-happen/commit/24a7ddd3a6970cc9b0d92807c9db002fcb53a913))
* update lru-cache requirement from ^7.4.4 to ^7.5.0 ([#119](https://www.github.com/npm/make-fetch-happen/issues/119)) ([5ef3bb3](https://www.github.com/npm/make-fetch-happen/commit/5ef3bb38b4fd122d5ffc012420e94a623a3d300d))
* update lru-cache requirement from ^7.5.0 to ^7.5.1 ([#120](https://www.github.com/npm/make-fetch-happen/issues/120)) ([8c5db07](https://www.github.com/npm/make-fetch-happen/commit/8c5db07f31f422de646026d7fb437bc4a6233473))
* update minipass-fetch requirement from ^2.0.2 to ^2.0.3 ([#114](https://www.github.com/npm/make-fetch-happen/issues/114)) ([bc71014](https://www.github.com/npm/make-fetch-happen/commit/bc71014c485a6963d8b6f5d8a3af793465bf9b39))

### [10.0.5](https://www.github.com/npm/make-fetch-happen/compare/v10.0.4...v10.0.5) (2022-03-07)


### Bug Fixes

* add code property to unsupported proxy url error ([#112](https://www.github.com/npm/make-fetch-happen/issues/112)) ([569a613](https://www.github.com/npm/make-fetch-happen/commit/569a6136b0ded34edd5de3584f518233fc720fcd))


### Dependencies

* update lru-cache requirement from ^7.4.0 to ^7.4.1 ([#113](https://www.github.com/npm/make-fetch-happen/issues/113)) ([b7f3e28](https://www.github.com/npm/make-fetch-happen/commit/b7f3e28f07c0e023dc6b616f61957fc49b3fdd2c))
* update minipass-fetch requirement from ^2.0.1 to ^2.0.2 ([#109](https://www.github.com/npm/make-fetch-happen/issues/109)) ([4a9892a](https://www.github.com/npm/make-fetch-happen/commit/4a9892a0fbf79965ed272d9bc5422c4525e7a990))

### [10.0.4](https://www.github.com/npm/make-fetch-happen/compare/v10.0.3...v10.0.4) (2022-03-02)


### Dependencies

* bump minipass-fetch from 1.4.1 to 2.0.1 ([#108](https://www.github.com/npm/make-fetch-happen/issues/108)) ([0257b63](https://www.github.com/npm/make-fetch-happen/commit/0257b637dde5831c9a9f1f652282d7818bebfa4a))
* update agentkeepalive requirement from ^4.2.0 to ^4.2.1 ([#102](https://www.github.com/npm/make-fetch-happen/issues/102)) ([0252efc](https://www.github.com/npm/make-fetch-happen/commit/0252efcb934c2b3d95af366d79b26d74aa477ca9))
* update lru-cache requirement from ^7.3.1 to ^7.4.0 ([#103](https://www.github.com/npm/make-fetch-happen/issues/103)) ([140ff64](https://www.github.com/npm/make-fetch-happen/commit/140ff64e90962ba5b8f7be7ef39446a669cfe572))

### [10.0.3](https://www.github.com/npm/make-fetch-happen/compare/v10.0.2...v10.0.3) (2022-02-15)


### Bug Fixes

* set agentkeepalive freeSocketTimeout back to 15 seconds ([#100](https://www.github.com/npm/make-fetch-happen/issues/100)) ([3371abf](https://www.github.com/npm/make-fetch-happen/commit/3371abf9e342d75bdc063b346bdefedd573f55a9))

### [10.0.2](https://www.github.com/npm/make-fetch-happen/compare/v10.0.1...v10.0.2) (2022-02-10)


### Dependencies

* update lru-cache requirement from ^7.3.0 to ^7.3.1 ([6ca02ad](https://www.github.com/npm/make-fetch-happen/commit/6ca02ad504a7eaf62e81cf170cd5e947ef79584d))

### [10.0.1](https://www.github.com/npm/make-fetch-happen/compare/v10.0.0...v10.0.1) (2022-02-09)


### Bug Fixes

* **agent:** don't use polynomial regex ([61856c6](https://www.github.com/npm/make-fetch-happen/commit/61856c65149f74ab353d8d6d401e90abb6f30950))


### Dependencies

* bump lru-cache from 6.0.0 to 7.0.1 ([3e353d2](https://www.github.com/npm/make-fetch-happen/commit/3e353d2bf7ce035346295eb5ffd5c2d169466537))
* update agentkeepalive requirement from ^4.1.3 to ^4.2.0 ([ed7f983](https://www.github.com/npm/make-fetch-happen/commit/ed7f98364f9a5b11c8fc5fd088c68d04df42415d))
* update cacache requirement from ^15.2.0 to ^15.3.0 ([46e0ac4](https://www.github.com/npm/make-fetch-happen/commit/46e0ac4f54a2cdf4ec925768238073ac941ed8d9))
* update lru-cache requirement from ^7.0.1 to ^7.3.0 ([e825c2c](https://www.github.com/npm/make-fetch-happen/commit/e825c2c26d41fe9076031c62827c5dc91898837e))
* update minipass requirement from ^3.1.3 to ^3.1.6 ([778c46a](https://www.github.com/npm/make-fetch-happen/commit/778c46a42e0e674d61bcce38cb248263c5a1149f))
* update minipass-fetch requirement from ^1.3.2 to ^1.4.1 ([6fabf4c](https://www.github.com/npm/make-fetch-happen/commit/6fabf4c23c8a33dce221ea2fac8cb1ecd14767a1))
* update socks-proxy-agent requirement from ^6.0.0 to ^6.1.1 ([58f3b29](https://www.github.com/npm/make-fetch-happen/commit/58f3b291eaec6bd6ce534de51ee8db9dd8348e4a))
* update ssri requirement from ^8.0.0 to ^8.0.1 ([5b75b08](https://www.github.com/npm/make-fetch-happen/commit/5b75b089a66c9c26564034d55dc0d04f5f59a515))

## [10.0.0](https://www.github.com/npm/make-fetch-happen/compare/v9.1.0...v10.0.0) (2022-01-25)


### ⚠ BREAKING CHANGES

* this drops support for node10 and non-LTS versions of node12 and node14

### Bug Fixes

* Add year to license ([#68](https://www.github.com/npm/make-fetch-happen/issues/68)) ([d0d86eb](https://www.github.com/npm/make-fetch-happen/commit/d0d86eb42fa16b7d5de51d77c69255efb437daf6))
* compress option and accept/content encoding header edge cases ([#65](https://www.github.com/npm/make-fetch-happen/issues/65)) ([f7d1255](https://www.github.com/npm/make-fetch-happen/commit/f7d1255951f936713a260efc85d4727f2b05eafe))
* move to template-oss ([105872f](https://www.github.com/npm/make-fetch-happen/commit/105872f6fede073c1423d8b7548afdfcad06b89a))
* revert negotiator preload hack ([8688f09](https://www.github.com/npm/make-fetch-happen/commit/8688f0952cb5710f6e802ae2858d6f00efc2d71d))
* strip cookie header on redirect across hostnames ([#71](https://www.github.com/npm/make-fetch-happen/issues/71)) ([ec53f27](https://www.github.com/npm/make-fetch-happen/commit/ec53f27335a8d1b981c7d32e941e71e4d2851efb))
* Update inline license to use [@license](https://www.github.com/license) comment ([#67](https://www.github.com/npm/make-fetch-happen/issues/67)) ([f602e06](https://www.github.com/npm/make-fetch-happen/commit/f602e0644c435f7f68b5c17b1b275ad0829b260f))


### dependencies

* http-proxy-agent@5.0.0 ([0013272](https://www.github.com/npm/make-fetch-happen/commit/00132720316b4ed5df66240fe0860f914378addf))
* negotiator@0.6.3 ([70d3496](https://www.github.com/npm/make-fetch-happen/commit/70d3496dbf5badb1fae60fb6bf454313ee6d4648))
* npmlog@6.0.0 ([09ebad1](https://www.github.com/npm/make-fetch-happen/commit/09ebad1c3394ca430a0b65848e9169df1872a35c))
