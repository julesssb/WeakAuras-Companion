<template>
  <div id="help" ref="help">
    <div class="title">{{ $t("app.help.title" /* Setup steps */) }}</div>
    <ol class="follow">
      <li>
        {{
          $t(
            "app.help.s1" /* Configure WeakAuras Companion, you will need to at least set your World of Warcraft Folder and Account. */
          )
        }}
      </li>
      <li>
        {{
          $t(
            "app.help.s2" /* Click on 'Fetch Updates', this is also done automatically once every hour. */
          )
        }}
        <ol class="follow">
          <li>
            {{
              $t(
                "app.help.s2_1" /* Companion creates a list of your auras with a link to Wago. */
              )
            }}
          </li>
          <li>
            {{
              $t(
                "app.help.s2_2" /* Companion sends the list to the Wago API. */
              )
            }}
          </li>
          <li>
            {{
              $t(
                "app.help.s2_3" /* Wago sends updated import strings and Companion compares versions. */
              )
            }}
          </li>
          <li>
            {{
              $t(
                "app.help.s2_4" /* Companion creates a new "WeakAurasCompanion" addon automatically, this is where new import strings are saved. */
              )
            }}
          </li>
          <li>
            {{
              $t(
                "app.help.s2_5" /* Restart World of Warcraft or reload your UI. */
              )
            }}
          </li>
        </ol>
      </li>

      <li>
        {{
          $t(
            "app.help.s3" /* The first time you start WeakAuras Companion, you will have to restart the game for it to be able to load the addon. */
          )
        }}
      </li>

      <li class="reset">
        {{
          $t(
            "app.help.s4_1" /* Update your auras in-game by clicking the update button next to them */
          )
        }}
        <img :src="require(`@/assets/wagoupdate_logo.png`)" />
        {{ $t("app.help.s4_2" /* in the WeakAuras options. */) }}<br />
        <img :src="require(`@/assets/ingame.png`)" class="center" /><br />
        <img :src="require(`@/assets/diagram.gif`)" class="center" />
      </li>
      <li>
        {{
          $t(
            "app.help.s5" /* You can always skip a version or just ignore updates completely. */
          )
        }}<br />
        <img :src="require(`@/assets/ingame2.png`)" class="center" />
      </li>
    </ol>
    <br />
    <br />
    <div class="title">
      {{ $t("app.help.auraAuthorsTitle" /* Tips for Authors */) }}
    </div>
    <div class="paragraph">
      {{
        $t(
          "app.help.auraAuthorsText1" /* If you publish auras on Wago, we recommend these settings: */
        )
      }}
      <ul>
        <li>
          {{
            this.$t(
              "app.help.auraAuthorsText2" /* In the Companion App, write your Wago username into the "Wago Account" setting. */
            )
          }}
        </li>
        <li>
          {{
            this.$t(
              "app.help.auraAuthorsText3" /* In WeakAuras, select the "Ignore all Updates" option for any aura you've modified heavily. */
            )
          }}
        </li>
      </ul>
      <br />
      <br />
    </div>
    <div class="title">{{ $t("app.help.foundbug" /* Found a bug? */) }}</div>
    <div class="paragraph">
      {{
        $t(
          "app.help.bug" /* If you encounter a bug, please create a ticket on */
        )
      }}
      <a
        target="_blank"
        href="https://github.com/WeakAuras/WeakAuras-Companion/issues/new"
        >GitHub</a
      >
      {{ $t("app.help.bugend" /* containing: */) }}<br />
      <ul>
        <li>
          {{ $t("app.help.bug.s1" /* A description of your problem. */) }}
        </li>
        <li>{{ $t("app.help.bug.s2" /* The steps to reproduce it. */) }}</li>
        <li>
          {{
            $t(
              "app.help.bug.s3" /* A screenshot if it helps to understand your issue. */
            )
          }}
        </li>
        <li>
          {{
            $t(
              "app.help.bug.s4" /* Error logs, type Ctrl+Shift+I to access the console and copy any error that might show up. */
            )
          }}
        </li>
      </ul>
    </div>
    <br />
    <br />
    <div class="title">{{ $t("app.help.support.title" /* Support */) }}</div>
    <div class="paragraph">
      {{
        $t(
          "app.help.support.text1" /* If you need more help come talk with us on WeakAuras's */
        )
      }}
      <a href="https://discord.gg/wa2" target="_blank">Discord</a>
      {{ $t("app.help.support.text2" /* #Companion-Help channel. */) }}
    </div>
    <br />
    <br />
  </div>
</template>

<style scoped lang="scss">
#help {
  padding: 10px 2.35vw;
  text-align: left;
  height: 100%;
  position: relative;
  overflow: auto;
  font-weight: 500;
}
.updateButton {
  margin-left: 60%;
}
#help > ol {
  margin-left: 15px;
  padding-left: 0;
}
ol,
ul {
  font-family: "Source Sans Pro", sans-serif;
  font-size: 15px;
  margin-left: 30px;
}
.follow {
  counter-reset: item;
}
.follow > li {
  display: block;
  margin-top: 5px;
}
.follow > li:before {
  content: counters(item, ".") ". ";
  counter-increment: item;
}
li > img {
  transform: translate(0, 8px);
}
.center {
  position: relative;
  left: 50%;
  transform: translate(-50%, 0);
  margin: 20px 0 0;
  max-width: 100%;
}
a {
  color: rgb(255, 209, 0);
  font-weight: 700;
}
a:hover {
  color: rgb(255, 228, 106);
}
.reset {
  margin-top: 0px !important;
}
.paragraph {
  margin-left: 15px;
  font-family: "Source Sans Pro", sans-serif;
}
</style>
