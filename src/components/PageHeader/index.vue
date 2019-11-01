<template>
  <header class="page-header">
    <!-- 桌面版	 -->
    <div class="d-header">
      <nav class="d-nav">
        <div class="d-left">
          <h1 class="d-brand">
            <router-link to="/" class="d-brand-logo" />
          </h1>
        </div>

        <ul class="d-navigation">
          <li class="active">
            <router-link class="d-menu" exact to="/">首页</router-link>
          </li>
          <li>
            <router-link class="d-menu" exact to="/">菜单1</router-link>
          </li>
          <li>
            <router-link class="d-menu" exact to="/">菜单2</router-link>
          </li>
          <li>
            <router-link class="d-menu" exact to="/">菜单3</router-link>
          </li>
          <li>
            <router-link class="d-menu" exact to="/">菜单4</router-link>
          </li>
        </ul>

        <div class="d-right">
          <el-button round>圆角按钮</el-button>
          <el-button type="primary" round @click="$router.push({path: '/login'})">登录</el-button>
        </div>
      </nav>
    </div>

    <!-- 移动版 -->
    <div class="m-header">
      <div class="m-top" />

      <nav class="m-nav" />
    </div>
  </header>
</template>

<script>
export default {
  name: 'PageHeader',
  props: {

  },
  watch: {
    $route(route) {
      console.log(route)
    }
  },
  methods: {

  }
}
</script>

<style lang="scss">
$headerHeight: 88px;
$headerHeight1280: 74px;
$headerHeight1024: 64px;

.portal-page {
	-webkit-font-smoothing: auto;
	background-color: #fff;
	padding-top: $headerHeight;
	min-height: 100%;
	position: relative;
}

.page-header {
	width: 100%;
	position: fixed;
	top: 0;
	right: 0;
	left: 0;
	z-index: 9;
	background-color: #fff;
}

.d-header {
	width: 100%;
	height: $headerHeight;
	box-sizing: content-box;
	transition: top .4s cubic-bezier(.19, 1, .22, 1);
	box-shadow: 0 4px 20px rgba(44, 114, 255, .05);
	border-bottom: 1px solid rgba(44, 114, 255, .1);

	.d-nav, .d-left, .d-right, .d-brand, .d-navigation, .d-menu {
		display: flex;
		align-items: center;
		justify-content: center;
		height: 100%;
		box-sizing: border-box;
	}
}

.d-nav {
	position: relative;
	width: 100%;
	min-width: 1024px;

	.d-navigation {
		margin: 0;
		padding: 0;
		width: 100%;
		list-style: none;

		li {
			padding: 0 32px 0 0;
			height: 100%;
			font-size: 16px;

			.d-menu {
				position: relative;
				width: 100%;
				transition: all .6s cubic-bezier(.19, 1, .22, 1);

				&:after {
					content: '';
					display: inline-block;
					position: absolute;
					bottom: -1px;
					left: 50%;
					height: 6px;
					width: 0;
					z-index: 10;
					border-radius: 3px;
					transform: translateX(-50%);
					transition: all .6s cubic-bezier(.19, 1, .22, 1);
				}
			}

			&:last-child {
				padding: 0;
			}

			&:hover {

				.d-menu {
					color: #296bef;
					font-weight: 500;
				}
			}

			&.active {

				.d-menu {
					color: #296bef;
					font-weight: 500;

					&:after {
						width: 40px;
						transform: translateX(-50%);
						background-color: #296bef;
					}
				}
			}
		}
	}

	.d-left, .d-right {
		position: absolute;
		top: 0;
		bottom: 0;
	}

	.d-left {
		left: 40px;
	}

	.d-right {
		right: 40px;
	}

	.d-brand {
		margin: 0;
		padding: 0;
		transform: translate3d(0,0,0);
		transition: all .4s cubic-bezier(.19,1,.22,1);

		.d-brand-logo {
			display: inline-block;
			width: 177px;
			height: 32px;
			background-image: url(../../assets/img/logo.png);
			background-repeat: no-repeat;
			background-position: 0 center;
			background-size: 177px 32px;
		}
	}
}

.d-header, .m-header {
	overflow: hidden;
}

.m-header {
		display: none;
		height: $headerHeight1024;
}

@media screen and (max-width: 1280px) and (min-width: 1025px) {
	.portal-page {
		padding-top: $headerHeight1280;
	}

	.d-header {
		height: $headerHeight1280;
	}

	.d-nav {
		.d-navigation {
			li {
				font-size: 14px;
			}
		}

		.d-left {
			left: 20px;
		}

		.d-right {
			right: 20px;
		}
	}
}

@media screen and (max-width: 1024px) {
	.portal-page {
		padding-top: $headerHeight1024;
	}

	.d-header {
		display: none;
	}

	.m-header {
		display: block;
	}
}
</style>
