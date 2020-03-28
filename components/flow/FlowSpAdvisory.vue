<template>
  <div :class="$style.container">
    <dl>
      <div>
        <dd>
          <div :class="[$style.phone, $style.fzNumeric]">
            <span :class="$style.icon">
              <PhoneIcon alt="Phone" />
            </span>
            <a href="https://www.pref.wakayama.lg.jp/prefg/041200/d00203179.html">新型コロナウイルス感染症専用相談窓口</a>
          </div>
          <div
            v-if="!['ja', 'ja-basic'].includes($i18n.locale)"
            :class="[$style.phone, $style.fzNumeric]"
          >
            <span :class="[$style.fzMedium, $style.break, $style.mb10]">
              {{ $t('ひまわり') }}
            </span>
          </div>
        </dd>
      </div>
    </dl>
  </div>
</template>

<script lang="ts">
import PhoneIcon from '@/static/flow/responsive/phone.svg'

export default {
  components: { PhoneIcon }
}
</script>

<style module lang="scss">
@import '@/components/flow/flow_sp.scss';

// advisory
.open {
  margin-top: px2vw(20);
  display: flex;
  justify-content: center;

  > span {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: $white;
    color: $green-1;
    padding: px2vw(20) px2vw(40);
    border-radius: px2vw(6);
  }
}

.daytime {
  margin-top: px2vw(20);
  display: flex;
  border-top: 1px solid $gray-4;
  border-bottom: 1px solid $gray-4;

  > * {
    padding: px2vw(30) px2vw(10);
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .title {
    text-align: center;
    flex-basis: 40%;
  }

  .link {
    flex-basis: 60%;

    > a {
      text-decoration: none;
    }
  }
}

.night {
  margin: px2vw(30) auto;
  padding-left: 0 !important;
  text-align: center;

  > li {
    list-style-type: none;

    &:not(:first-child) {
      margin-top: px2vw(20);
    }
  }
}

@include largerThan($small) {
  $vw: 960;

  .open {
    margin-top: px2vw(20, $vw);

    > span {
      padding: px2vw(20) px2vw(40, $vw);
      border-radius: px2vw(6, $vw);
    }
  }

  .daytime {
    margin-top: px2vw(20, $vw);

    > * {
      padding: px2vw(30) px2vw(10, $vw);
    }
  }

  .night {
    margin: px2vw(30, $vw) auto;

    > li {
      &:not(:first-child) {
        margin-top: px2vw(20, $vw);
      }
    }
  }
}
</style>
