<script>
	import Fa from 'svelte-fa';
	import { faBell } from '@fortawesome/free-regular-svg-icons';
	import { faUser, faEye, faFaceSmile, faComment } from '@fortawesome/free-regular-svg-icons';
	import { faBlog } from '@fortawesome/free-solid-svg-icons';
	import User from '$lib/components/User.svelte';
	import PostBanner from '$lib/components/PostBanner.svelte';

	let name = 'Ritom Ghosh';

	let userSatisfaction = '80';
</script>

<div class="body">
	<ul class="info">
		<div class="readers info-card-wrapper">
			<div class="info-card">
				<h2>720</h2>
				<h2>Daily readers</h2>
			</div>
			<Fa icon={faUser} size="lg" style="color:var(--text);" />
		</div>
		<div class="posts info-card-wrapper">
			<div class="info-card">
				<h2>1214</h2>
				<h2>Total posts</h2>
			</div>
			<Fa icon={faBlog} size="lg" style="color:var(--text);" />
		</div>
		<div class="views info-card-wrapper">
			<div class="info-card">
				<h2>15000</h2>
				<h2>Total views</h2>
			</div>
			<Fa icon={faEye} size="lg" style="color:var(--text);" />
		</div>
		<div class="satisfaction info-card-wrapper">
			<div class="info-card">
				<h2>{userSatisfaction}%</h2>
				<h2>Users satsified</h2>
			</div>
			<Fa icon={faFaceSmile} size="lg" style="color:var(--text);" />
		</div>
		<div class="comments info-card-wrapper">
			<div class="info-card">
				<h2>920</h2>
				<h2>Total comments</h2>
			</div>
			<Fa icon={faComment} size="lg" style="color:var(--text);" />
		</div>
	</ul>
	<div class="line" />
	<h1 id="posts-title">Top Posts</h1>
	<div class="top-posts">
		<PostBanner
			title="How I published my flutter app using Github actions"
			desc="Publishing a Flutter app can be an exciting yet daunting task. From building the app to preparing it for release and managing the deployment process, there are several steps involved. One way to simplify and automate this process is by using GitHub Actions. In this blog post, I'll walk you through the steps I took to publish my Flutter app using GitHub Actions, making the deployment process smooth and hassle-free."
		/>
		<PostBanner
			title="How I write programs easily and fast with knowledge and AI"
			desc="In the world of programming, efficiency and productivity are highly valued. Whether you're a seasoned developer or just starting your coding journey, the ability to write programs quickly and effectively is a skill that can significantly impact your success. With the advent of Artificial Intelligence (AI) and access to vast amounts of knowledge, programming has become more accessible and efficient than ever before. In this blog post, we'll explore how knowledge and AI can help you write programs easily and fast."
		/>
		<PostBanner
			title="How I Created Blauga: The Number One Platform for Blog Writers"
			desc="Blauga, a platform designed exclusively for blog writers, has quickly risen to become the premier destination for bloggers worldwide. But building a successful platform like Blauga is no small feat. In this blog post, I will take you on a journey through my experience of creating Blauga, sharing the challenges, strategies, and lessons learned along the way."
		/>
	</div>
	<h1 id="posts-title">Latest Posts</h1>
	<div class="top-posts">
		<PostBanner
			title="How I published my flutter app using Github actions"
			desc="Publishing a Flutter app can be an exciting yet daunting task. From building the app to preparing it for release and managing the deployment process, there are several steps involved. One way to simplify and automate this process is by using GitHub Actions. In this blog post, I'll walk you through the steps I took to publish my Flutter app using GitHub Actions, making the deployment process smooth and hassle-free."
		/>
		<PostBanner
			title="How I Created Blauga: The Number One Platform for Blog Writers"
			desc="Blauga, a platform designed exclusively for blog writers, has quickly risen to become the premier destination for bloggers worldwide. But building a successful platform like Blauga is no small feat. In this blog post, I will take you on a journey through my experience of creating Blauga, sharing the challenges, strategies, and lessons learned along the way."
		/>
	</div>
</div>

<div class="creator-notifs">
	<div class="creator">
		<div><Fa icon={faBell} size="lg" style="color:var(--text);" /></div>
		<img
			class="creator-img"
			src="https://lh3.googleusercontent.com/pw/AIL4fc_GiOBlGmMtARAOx-IM3i64P6hnea5OyLdvaqTSmOG9GFMenMfjLy6Z2U1b8jZtuw_ZF15mG_2UBfI9u-I8E7P5v2gPlZYcIwaNygsOVUXBWiS15y9JQnL3LVkIVX1yy68WKSxy66pqU4fgEv_A7elqIvsJ5dKlKo35FtiiU2J5FUMFGm6YdDlO_dpzmbb37EP17Gi2kilbuvh_IVnbVHdh1QOhRL28-y4Ss1abCmTkOvA4cMa2QPqs2Pre_zSNIYhRKaWdgdLtTM9nGEU5g10NsjJYJIfHvNKAOULMvEB05CdlKmaDHLyJCMqkSLc03aeh8Z0EnyjMMll8ewTtmUZybar8yPUEA1UbQ3mELnzYW59Cp1cM_H8mAGWat8XONvQG9bnk5L9_eIOUPDoeh_lXmVxb7J8RK5EXRcw0GD7RbST2bsAux35ojH_O0YnMZVql5713VxvvjrXrpFtHuvNVcHjuFKeZgtPvmtuTDD5XYfqCe7XArML-gGipnvaljca5_qc8F_Znswmj-Y8loglK60nRlcR_al9oynvMcDDN7eepaU2f0p1beF_Takp29xS3xThYjfKSUkKiJEi9DwZ5MecIlDx4ZfntB7BRRhgF9BUrtueuTJS9qfmyXt9gp-P8Iq3Q2WyDzPGCED8wcGYclFojwrvWoAiCAlsZ5BlcLEMjxIyMrJCPOe11OJeTNkfa5wLy0hCYqg_Tik_vnQm7c5O6EX2rrAbHPO6CTd19-wc1buC1lkMPtWVvyWmL4Io1w3VT6UqyqeM3evEIfC50oEHUJ193JYHz35YohM4Drnukqe1iGpTmYmaDTsHYkeJ8m9Yustl8oNF1WhvthgF5v3DsbHM3vuaCizSDaAYDhxq71VyFVu8ecEc5ECfqKE_QVFVIMqPIQGwynX8IJoeCxZM=w610-h610-s-no?authuser=0"
			alt="Blauga creator Ritom"
		/>
		<h2 class="creator-name">{name}</h2>
	</div>
	<div class="line" />
	<ul class="top-readers">
		<h2>Top Readers</h2>
		<User
			img="https://lh3.googleusercontent.com/pw/AIL4fc_80Ffv3OFTN95ica4ACx13Fj0HL4V0fsqDv3sYxovDYX46eLBRwDsiEQfgfBSz73GxSApFjad8Nyy-oZ-5ys7lCRO28pXIsBnnOmOslyc1Yd1mjxryZ4SAlAjcHnrc1DKifzMJQpce9JwyH0ZNYhIk9rIPhGsIe-KYJAM1KiYbZcnJ6DzPH7QNf8uRGn6tWs47zbx3UcbhgJyW7f1yPNPCWLzjhv7KZjTcmSls-QnKzLtImir0qwiStCFx0toJwVnZWqXLDQy9Fi5szvMMD8rEHLDqv2fr1-zZAPjWum0qXSmAfuDIPZqfEV-4MQwMFBw5R5idld9k2_7xd1QGb4XRtw8FEaQ7yO47qxESiiUQjvs_-MNvsAmuoGwkktCCMH49vDlL-1oxS--wrycf0aNKOPMxazANK5x9RYx23bD-eA7vjhG4QqF4zPDZtYE6r0aSdnlh_hoHvB9lRKzlhQhiE0qKCQal5R5lSFsC0OoyMyR28hP3lmrZUFuvoZfNPYl7cTxE3vjnDPJADereeHWYoj2QD6IJMz0MtPjN1FFbcKdxfwLa4oKCcFR8MYLP-gdYaihZj5orFpyFvVA5Ntye95EhlVKySQfomPPfnJJh-S3czlE0oC0GChmWY9l41kwRgcqhELQvv7ZxTpjTXc3yg6JsnUh0NbLi0mtDayRFiDKFOXKhpA4YSbZeij8i19yhtxzaj_OGVlmu5ldLYrBpMUs9NxpMWjIJM2EDRL4fL0rFVXsh6uHGTkBAVopvdtBmbLRSp9_WmCAZOGwDFS-DyxRJ6_H9x-4dkHA76uD36_Mjyr7MyAwkC5WR4FB-ii7eTYrd3PozfLWJjWikPwkEKu8ZaJiq7sNBsXyTmLTUldz873rVsgMP13Vocp4KWWJ8KUIF7WZ73309UB2i4OBt6tc=w343-h610-s-no?authuser=0"
			name="Rahul Ghosh"
		/>
		<User
			img="https://lh3.googleusercontent.com/pw/AIL4fc8eMwbu7I9HA3dcwbHcMktdwEqNlDCfOS-EbsYQDqwW23Eo3r1iKDhJCI9JucgAKa4yFAZdCz3D7W9jPRg4DzmoZjFbHBenxxcxT6Pm3goOLj8liD8xFkhy8XvJMSm1Y3fz243Ogsk5Qsy0e59EAhqshfVEBzqs54aw2IzlsrgaDCc0U5NI6NsMFLzBOiRTblUA3VWw5Mw1ykLQX6egQo-2TTysLphNgdN1yYcbJMFwv0JRIuRN4pqJQjPyzAajkAfjS1O7QdHOpREroSAfWc-qcKDY4JWwQoHwGQZvQi_kgmCdQC6Q23KAKhz_kxilPwhAecXMjadJ70Hd_MD4pxR8czmSa531nps0EPX6jVyPM2RJAOcMaCyiXX000GtWDJ1GipN4hiz_kGYxhFg8JsTCeYA4LsoVCzKzLDJbDw_Lv-51BLdH0LB3OJBlzy6CGOzTzOvNSJCaZ-pYcvOQfKyHvbH5doWwDRysHlqE0H0yhgcjO30-GXC_Pm4dqKxq4O8TnpQOUtWPSq3U6mhqrYdH20yMX20zm9FzlTQJ5lcq_jUJOYtLgWbeL25lZ06ul3Scv_hAkHBp8CK7ywWktzmq0U1S9dJJGtlL-SIvokhjqfKCiNngV0sXGO-JkPHrCiSA3OuwEfEvggRUXwuG0L3CI1If9uYe3dV1zj9a3b_u2p650AlQFeFqHLNZRKJcvYZYrqAFwdjTeA47_mOEybkTl4pKaX7YHz-WyMcH_Tf5Mz-IU9bswzIoUlbhwvQ0j9QDZTpRGN0OufGmo3fJbMP952VFsoJTsb3MlE1JbiX6ngQ4Hsetg_qhOPncTbdGzFXe4Q0g4BQxs7lh21z1f2yGlLXSfBeFAfn9KaNdqvY-I0KszkE4Tyg6Q1Uu3VC6gyWJtZCaWA089eJ4Picd-6uOlA=w594-h610-s-no?authuser=0"
			name="Jeet Ghosh"
		/>
		<User
			img="https://lh3.googleusercontent.com/pw/AIL4fc-EIHO-OILtTRhevToxPSg40S7D6LvEQLBz5uHPGQSL4gTNFr5lUcsnWrUHg-2JOvBo8ziPdQ-q_YW2kpql4SCI839Eqbbu1aKm2fV5CG5HwmIG8HkwIiApvS-yxnsy43QnPG2lPj0Ua52XNJcO2tUh4oozwiBkJRqDHkFNcyd_G7_0k1WG4TV6JRDeJsW4N41nDBTmwZ2K8qOOXA5UbkqXlS07K9pOpx5vZErII6Aniu78OIiwTFu04njPgwgxpnOCffineW3pHrv5LDfG7dWPl3EVTYTsKOrkn_CM3mTXwCx4keehTAq4F3AUIvNRGTbB55g-5vMd7sBc_hfKhbkT7CcbwHe5_fpZvywMTtYKo4TxONWPkdh_KE0509E_cbsAJMkgQsNKuXbQpQOhFUBYeza44Zg4UcsaPk0iM7gGxcM8vr9h0bTOUPKBm24aPLT2keTqcof0E9HVV87w4O7BogmJQb70Q_FUl0hdKbyirFYZzD6F8AutI77qyHCAke68feUiGumYc_gCxuY57THsTH02m5p7xG4q-8gYATuGJVVygWu9Kbl3cCX1IR9Ilmn7Doivc5n22ct3E0Jf77U1gw7EEP6q0iVtsyloN_znlJHz_OsW8bh6L99d0oliz1DAGRngCZsfyx6itzeDXtzkDTdv3khLg02yOJ_mw1W8oZG166Zw3Pul_fRIPl-X33J0P79k8d-h0s_v6J_kUglTdUvJQfYRXvVdDXHeApR7XXVRUI2iZjCe6TaxxFP3F9RnOGn9saFrRV4wDdjkmry_O7DZMWpvZCtAVO2RPVftGKAsM1ooN6Qhx6YfDO-qP0bsys0VgNgnknfJBxKjjEryQMrLqqUf3DfVwX3o5J3yNDiEd0JsoOF5RATLfFouklXdodg_xTF83SuL_Gp3H61HLg=w165-h220-no?authuser=0"
			name="Ritwik Ghosh"
		/>
		<User
			img="https://lh3.googleusercontent.com/pw/AIL4fc_nSVj_hMGXPNC9cP2z1QnzvXQBAu3L5Uz5McPcTx7rbwx8Hd0ywempc3wVLEbQbZ5AG6XiDHgEpHfzcrR7JlZplirR9-w-iQrcHGVMroVmbZgE3ApnrlKtYmaAxDiXDi7JY8VMWVwhYfq_f96tBzJH_JnuUg0HbbvY3sntXpIESKQ07N09QBwBURcLvxnBujnUe6MgL4jSxT2P7JnjJEVGDxORbpKuyqf8crXN70UqaNJPnvRXZ86FJnwTuY-_pWs6Dou5g7wVKZxN0yQa-VXUNUCNPWUR4neTKZMwvogcmuuuJogZclXZ_6HucecAQN8oDSI2blhXESassm9m245g8s6qM3ZUda1y1ELe0UWbfgQCc9QwSvlKJY1So413C3ENyLpkXGC_rVeJP5JUgkNUo0Cs54Bclb08OvNy1cbT39PhfX1Lsz10YzFf20Qq_9SOedgb3qihNPkVhfpIZecEcS46UCFKjNlebCu545-Lcj_4EH2psrmFtp-aYk-oInBTBNz8JLPCt7vwz_GDB08bdNMLnqSpuveRm2TwWF15mrd9bS9J9-6w3asn1bYiqz8dcdLpRrdbs3_wXhHiuJgR-fP0iALuSfoDR3YiWs9G0rdgYUzblw7YxYRC2Jbo8CvDjwswqkl6h41OQoDZBrSAGVrahVG0LLTxaY81-xsBc4OG10IdUVthNSYUxBfpn3RJTp9P3j7xC_kLz2jsXCEKG7i-Jb9qMbjcIxvuZRTsmyith5VfdHyWvIiY75HooQll113mEa2f3LMBkDvgGPAUjo5iR3mgB4cr_WoCL5goKK_F8XkENpnd_8F7Dz_4LFGHQcBBocPFNyJIoYNb6pFJrjW-RpxI8x7tobtVprb9ViDOUKdpoCVQfUW__u40xjO7aphx0Hd1BnjXcEbdC8pfzg=w181-h240-no?authuser=0"
			name="Pijush Ghosh"
		/>
		<User
			img="https://upload.wikimedia.org/wikipedia/commons/thumb/3/34/Elon_Musk_Royal_Society_%28crop2%29.jpg/1200px-Elon_Musk_Royal_Society_%28crop2%29.jpg"
			name="Elon Musk"
		/>
		<User
			img="data:image/jpeg;base64,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"
			name="Bill Gates"
		/>
	</ul>
	<div class="line" />
	<div class="user-satisfaction">
		<h2>User Satisfaction</h2>
		<div role="progressbar" style="--value:{userSatisfaction}" />
	</div>
</div>

<style>
	#posts-title {
		margin-left: 1rem;
	}
	.info {
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		gap: 8px;
		margin-left: auto;
		margin-right: auto;
		flex-wrap: wrap;
	}
	.info-card-wrapper {
		width: 8rem;
		height: 5rem;
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		gap: 1rem;
		background: linear-gradient(45deg, var(--accent) 0%, var(--accent30) 100%);
		padding: 12px;
		border-radius: 16px;
	}
	.info-card {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		gap: 1px;
		margin: 0;
	}
	.info-card h2 {
		margin: 0;
		padding: 0;
		text-align: center;
		font-size: 1.2rem;
	}
	.creator-notifs {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		gap: 1rem;
		margin-left: auto;
	}
	.creator {
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		gap: 1rem;
	}
	.creator-img {
		width: 3rem;
		height: 3rem;
		border-radius: 50%;
	}
	.top-readers {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		gap: 0.2rem;
		margin-left: auto;
		margin-right: auto;
	}

	.top-posts {
		display: grid;
		gap: 0.4rem;
		grid-template-columns: 1fr 1fr 1fr;
	}

	@media (max-width: 768px) {
		.info-card-wrapper {
			width: 4rem;
			height: 3rem;
		}
		.info-card h2 {
			font-size: 0.7rem;
		}
		.top-posts {
			grid-template-columns: 1fr 1fr;
		}
	}

	@keyframes growProgressBar {
		0%,
		33% {
			--pgPercentage: 0;
		}
		100% {
			--pgPercentage: var(--value);
		}
	}

	@property --pgPercentage {
		syntax: '<number>';
		inherits: false;
		initial-value: 0;
	}

	div[role='progressbar'] {
		--size: 6rem;
		--fg: var(--primary);
		--progress-bg: var(--secondary);
		--pgPercentage: var(--value);
		animation: growProgressBar 3s 1 forwards;
		width: var(--size);
		height: var(--size);
		border-radius: 50%;
		display: grid;
		place-items: center;
		background: radial-gradient(closest-side, var(--bg) 80%, transparent 0 99.9%, white 0),
			conic-gradient(var(--fg) calc(var(--pgPercentage) * 1%), var(--progress-bg) 0);
		font-family: Helvetica, Arial, sans-serif;
		font-size: calc(var(--size) / 5);
		color: var(--text);
	}

	div[role='progressbar']::before {
		counter-reset: percentage var(--value);
		content: counter(percentage) '%';
	}

	.user-satisfaction {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		gap: 0.2rem;
		margin-left: auto;
		margin-right: auto;
	}

	.line {
		width: 15rem;
		height: 2px;
		background-color: var(--secondary);
		margin: 0;
	}
</style>
