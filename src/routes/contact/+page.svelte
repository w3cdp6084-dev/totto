<svelte:head>
	<title>Contact</title>
	<meta name="description" content="Contact page" />
</svelte:head>
<script>
	import Heading from '../../lib/Heading.svelte';
</script>

<Heading level={2} text="contact"/>
<div class="wrap">
	<div class="inner">
		<Heading level={3} text="Form" />
		<form class="form">
			<label for="name">お名前 <span>必須</span></label>
			<input type="text" id="name" name="name" />
			<label for="email">メールアドレス <span>必須</span></label>
			<input type="email" id="email" name="email" />
			<div class="radio-group">
				<input type="radio" id="request" name="inquiry-type" value="制作の依頼" />
  				<label for="request">制作の依頼</label>
  				<input type="radio" id="partnership" name="inquiry-type" value="パートナーシップ" />
  				<label for="partnership">パートナーシップ</label>
  				<input type="radio" id="other" name="inquiry-type" value="その他" />
  				<label for="other">その他</label>
			</div>
			<label for="message">お問い合わせ詳細 (1000文字以内) <span>必須</span></label>
			<textarea id="message" name="message"></textarea>
			<button type="submit">送信</button>
		</form>





	</div>
</div>





<style lang="scss">
	.wrap {
		max-width: 800px;
		margin: 40px auto 0;
		background-color:	#fff;
		border-radius: 16px;
	}
	.inner {
		padding: 24px 200px;
		.form	{
			display: grid;
			input {
				padding: 8px;
				border-radius: 8px;
				border: none;
				background-color: #F6F6F6;
				height: 36px;
				outline: none;
			}
			textarea	{
				padding: 8px;
				border-radius: 8px;
				border: none;
				margin-bottom: 16px;
				background-color: #F6F6F6;
				height: 160px;
				resize: none;
				outline: none;
			}
			label {
				margin-bottom: 8px;
				color: #3A3A3A;
				font-size: 0.9rem;
				span{
					color: #ff0000;
					font-size: 0.6rem;
				}
			}
			.radio-group {
				display: flex;
				align-items: center;
				margin-bottom: 16px;
			}

			.radio-group label {
				position: relative;
				display: inline-block;
				padding-left: 30px;
				cursor: pointer;
				user-select: none;
			}

			.radio-group input[type="radio"] {
				opacity: 0;
				position: absolute;
				width: 0;
				height: 0;
				margin: 0;
				padding: 0;
			}

			.radio-group label:before {
				content: '';
				position: absolute;
				left: 0;
				top: 0;
				width: 20px;
				height: 20px;
				border-radius: 4px;
				background-color: #F6F6F6;
				cursor: pointer;
			}

			.radio-group input[type="radio"]:checked + label:before {
				background-color: #F6F6F6;
			}

			.radio-group input[type="radio"]:checked + label:after {
				content: ''; 
				position: absolute;
				left: 5px;
				top: 9px;
				width: 6px;
				height: 11px;
				border: solid #3a3a3a;
				border-width: 0 3px 3px 0;
				transform: rotate(45deg);
			}

			button {
				grid-column: 1 / -1;
				padding: 8px 16px;
				border-radius: 8px;
				background-color: #E3E3E3;
				color: #fff;
				cursor: pointer;
				width: 240px;
				height: 60px;
				margin:	24px auto;
				border: none;
			}
		}
	}
</style>