<script lang="ts">
	import { AccordionItem, Accordion } from 'flowbite-svelte';

	// FORMSUBMIT, NUCLEUS GIVING, WEB3FORMS,
	// ASTRO: https://preview.tailus.io/astrolus-free/

	const ACCESS_KEY: string = 'c585df36-f878-451f-918b-dc23e8941a76';

	interface BeliefInfo {
		title: string;
		content: string[];
	}

	interface MinistryInfo {
		title: string;
		image?: string;
		description: string[];
	}

	const slugify = (s: string) =>
		s
			.normalize('NFKD') // handle accents/diacritics
			.replace(/['’]+/g, '') // drop straight & curly apostrophes
			.toLowerCase()
			.replace(/[^a-z0-9]+/g, '-') // collapse runs of non-alnum to "-"
			.replace(/^-+|-+$/g, ''); // trim leading/trailing "-"

	const ministryInformation: MinistryInfo[] = [
		{
			title: 'Preaching',
			image: `https://ik.imagekit.io/bip1v395ybp/Emmanuel%20Baptist%20Church/PREACHER2_Rz0apm1s3.jpg?updatedAt=1733800042663`,
			description: [
				`"For after that in the wisdom of God the world by wisdom knew not God, it pleased God by the foolishness of preaching to save them that believe." (1 Corinthians 1:21)`,
				'By this passage, we understand that preaching of the Bible is God’s method of reaching the unsaved. Though this method may stand against the way common wisdom would seek to reach a people group, this is the ordained method of God. Through preaching is God’s Word able to be made clear to the human mind and applied to the human heart.',
				'In our church, we highly regard the preaching ministry of our Pastor. It is God’s means for His church to be guided, encouraged and taught by preaching. At Emmanuel, there is nothing more central to our services than the message of God’s Word being delivered.'
			]
		},
		{
			title: `Student Ministry`,
			description: [
				'The teen years can be some of the most stressful and frustrating days of life. So far, life has seemed pretty simple. You wake up, put on the clothes your mom picks out for you, and head off to a school where you walk in a line and take naps after lunch. But somewhere along the way, middle-school happens, which is followed by something even more radical-high school! Life is fast!',
				'During these years, its so easy to get lost in the shuffle of school. So many wake up in their twenties and thirties realizing that they have made terrible mistakes in their teens and early twenties that could have been avoided. What may be even more tragic is the growing number of young adults who are leaving church, never to return.',
				'Our desire as a church is to reverse these trends beginning with our own teenagers. Teaching and instruction is given so that students can be grounded in their own faith in Jesus Christ; stable despite the seduction that fills our society.'
			]
		},
		{
			title: `Children's Ministry`,
			image: `https://ik.imagekit.io/bip1v395ybp/awana-clubs-logo-color_UjjD8b0RC.jpg?updatedAt=1756429228137`,
			// image: `https://ik.imagekit.io/bip1v395ybp/awana-clubs-logo-color-Photoroom_Jrnpd55-W.png?updatedAt=1756429237299`,
			description: [
				'Children are close to the heart of Emmanuel. As the future leaders of our church and community, we see it as one of our highest duties to teach the ways of God to the children of our church and to encourage them to live for Him. There are age appropriate classes for children ages 3-12 during the Sunday School and Sunday morning services. These classes are lead by capable and engaging teachers that desire to impact and encourage your child for Jesus Christ.'
			]
		},
		{
			title: `Music Ministry`,
			image: `https://ik.imagekit.io/bip1v395ybp/Emmanuel%20Baptist%20Church/John_8xDVTuwkap.JPG?updatedAt=1733800042636`,
			description: [
				'A Joyful Noise',
				`"O sing unto the LORD a new song: sing unto the LORD, all the earth.Sing unto the LORD, bless his name; shew forth his salvation from day to day.Declare his glory among the heathen, his wonders among all people." Psalm 96:1-3`,
				'Music, in sanctuary and home, should echo the greatness and glory of God. At Emmanuel, we see this as our highest goal in the music ministry. Our music is primarily directed toward God as a declaration of what He has done in our lives and hearts, proclaiming a complete dependence on and dedication to Christ’s work on the Cross.These verses from Psalm 96 capture the heart of what Christian music should be: praise to the Maker and Savior of man from a worship filled heart. Due to the wonder, awe and praise stored within the heart, the Christian should exclaim praise to God before a lost world: “He is the ‘rock of our salvation’, there is ‘no other God that can deliver’!” (Daniel 3:29). Through our songs and lives, may God be glorified and uplifted so that He might be seen as the God who is worthy of worship, praise and dedication.'
			]
		},
		{
			title: `Outreach`,
			description: [
				`At Emmanuel Baptist Church, we have a passion to reach our community, our country, and those around the world with the Gospel (Acts 1:8). Locally, we accomplish this through our bus ministry, and church-wide soul winning. Abroad, we accomplish this through our support of many missionaries. Currently, we support works in Moldova, Venezuela, Panama, China, India, Brazil, and a children's home in Brazil. In addition to supporting these works, we also support FBN radio which has a reach spanning the globe.`
			]
		}
	];

	const beliefInformation: BeliefInfo[] = [
		{
			title: 'The Holy Scriptures',
			content: [
				'We believe the Old and New Testament Scriptures as found in the Hebrew Masoretic Text and the Greek Received Text (Textus Receptus) are the verbally and plenarily inspired Word of God. The Scriptures are inerrant, infallible, and God-breathed. As such, these scriptures are the final authority for faith and practice. The sixty-six books contained in these Texts are the complete and divine revelation of God to Man. We believe that God kept His promise to preserve His Word to all generations (Psalm 100:5) and did so through the Hebrew Masoretic Text and the Received Text. The Scriptures are to be interpreted in context and light of the whole of scripture through a literal method of interpretation using normal grammatical-historical meaning. The Authorized King James Version of the Bible is currently the only English translation which is the preserved Word of God in that it is a formal equivalent (a word for word) translation of the preserved Hebrew Masoretic and Greek Received Texts. Therefore, it shall be the only translation used by the Church. All issues of interpretation and meaning shall be determined by the Pastor. (2 Tim. 3:16-17; 2 Pet. 1:20-21; Psalms 12:6-7; 100:5)'
			]
		},
		{
			title: 'Dispensationalism',
			content: [
				'We believe that the Scriptures interpreted in their natural, literal sense reveal divinely determined dispensations or rules of life that define man’s responsibilities in successive ages. These dispensations are not ways of salvation, but rather are divinely ordered stewardships by which God directs man according to His purpose. Three of these dispensations—the law, the church, and the kingdom—are the subjects of detailed revelation in Scripture. (Gen. 1:28; 1 Cor. 9:17; 2 Cor. 3:9-18; Gal. 3:13-25; Eph. 1:10; 3:2-10; Col. 1:24-25, 27; Rev. 20:2-6)'
			]
		},
		{
			title: 'The Godhead',
			content: [
				'We believe in one triune God, eternally existing in three persons—Father, Son, and Holy Spirit—each co-eternal in being, co-identical in nature, co-equal in power and glory, and having the same attributes and perfections.  (Deut. 6:4; Matt. 28:19; John 14:10, 26; 2 Cor. 13:14)'
			]
		},
		{
			title: 'The Person and Work of Christ',
			content: [
				'1. We believe that the Lord Jesus Christ, the eternal, sinless Son of God, became man, without ceasing to be God, having been conceived by the Holy Spirit and born of the Virgin Mary, in order that He might reveal God and redeem sinful men. (Isa. 7:14; 9:6; Luke 1:35; John 1:1-2, 14; 2 Cor. 5:19-21; Gal. 4:4-5; Phil. 2:5-8)',
				'2. We believe that the Lord Jesus Christ accomplished our redemption through His death on the cross as a representative, vicarious, substitutionary sacrifice, and that our justification is made sure by His literal, physical resurrection from the dead. (Luke 24:1-7, 39-42; Acts 2:18-36; Rom. 3:24-25; Eph. 1:7; 1 Pet. 2:24; 1 Peter 1:3-5)',
				'3. We believe that the Lord Jesus Christ ascended to Heaven and is now exalted at the right hand of God where, as our High Priest, He fulfills the ministry of Representative, Intercessor, and Advocate.  (Acts 1:9-10; Rom. 8:34; Heb. 9:24; 7:25; 1 John 2:1-2)'
			]
		},
		{
			title: 'The Person and Work of the Holy Spirit',
			content: [
				'1. We believe that the Holy Spirit as the third person of the Godhead convicts the world of sin, of righteousness, and of judgment; and, that He is the Supernatural Agent in regeneration, baptizing all believers into the body of Christ, indwelling and sealing them unto the day of redemption. (John 16:8-11; Rom. 8:9; 1 Cor. 12:12-14; 2 Cor. 3:6; Eph. 1:13-14)',
				'2. We believe that He is the divine Teacher who assists believers to understand and appropriate the Scriptures and that it is the privilege and duty of all the saved to be filled with the Spirit. (Eph. 1:17-18; 5:18; 1 John 2:20, 27) ',
				'3. We believe that God is sovereign in the bestowal of spiritual gifts to every believer. God uniquely uses evangelists, pastors, and teachers to equip believers in the church to do the work of the ministry. (Rom. 12:3-8; 1 Cor. 12:4-11, 28; Eph. 4:7-12) ',
				'4. We believe that the sign gifts of the Holy Spirit, such as speaking in tongues, the gift of healing, and the gift of prophesy were temporary. Speaking in tongues was a sign to unbelieving Jews that God was going to judge them for their apostasy. It was never the common or necessary sign of the baptism or filling of the Holy Spirit. Ultimate deliverance of the body from sickness or death awaits the consummation of our salvation in the resurrection, although God frequently chooses to answer the prayers of believers for physical healing. (1 Cor. 1:22; 13:8; 14:21-22)'
			]
		},
		{
			title: 'The Depravity of Man',
			content: [
				'We believe that man was created in the image and likeness of God; but that in Adam’s sin the human race fell, inherited a sinful nature, and became alienated from God. Man in his depraved state is unable of himself to remedy his lost condition. (Gen. 1:26-27; Rom. 3:22-23; 5:12; 6:23; Eph. 2:1-3; 4:17-19)'
			]
		},
		{
			title: 'Salvation',
			content: [
				'We believe that salvation is the gift of God brought to man by grace and received by personal faith in the Lord Jesus Christ, Whose precious blood was shed on Calvary for the forgiveness of our sins.  We believe that all sins, except blasphemy of the Holy Spirit, are forgivable.  (Matt. 12:31-32; John 1:12; Eph. 1:7; 2:8-10; 1 Pet. 1:18-19; 1 John 1:9)'
			]
		},
		{
			title: 'The Eternal Security and Assurance of Believers',
			content: [
				'1. We believe that all true believers are kept by God’s power, through faith, and are thus secure in Christ. (John 6:37-40; 10:27-30; Rom. 8:1; 38-39; I Cor 1:4-8; I Pet 1:4-5)',
				'2. We believe that it is the privilege of believers to rejoice in the assurance of their salvation through the testimony of God’s Word, which, however, clearly forbids the use of Christian liberty as an occasion to the flesh. (Rom. 13:13-14; Gal. 5:13; Titus 2:11-15) ',
				'3. We believe that the Word of God teaches the security of the believer, that God will keep securely in His hand (John 10:25-30) those who are trusting in Jesus, but offers absolutely no hope for that person who is not trusting in Christ (I Peter 1:5). The link that unites God and man is faith in Christ (John 3:16). The security of the believer is based upon a continuous faith in Jesus Christ (Col 1:21-23; John 3:16; Heb. 3:12-13). We believe that the Scriptures present the possibility of an authentic believer ceasing to believe (I John 2:24; Heb. 3:12-13) but not in the probability (Heb. 6:9). We believe that apostasy is committed by willful unbelief and is without remedy (Heb. 6:4). '
			]
		},
		{
			title: 'The Church',
			content: [
				'1. We believe that the church, which is the body and the espoused bride of Christ, is solely made up of born-again believers.  (1 Cor. 12:12-14; 2 Cor. 11:2; Eph. 1:22-23; 5:25-27)',
				'2. We believe that the establishment and continuance of local churches is clearly taught and defined in the New Testament.  (Acts 14:27; 20:17, 28-32; 1 Tim. 3:1-13; Titus 1:5-11)',
				'3. We believe in the autonomy of the local church free of any external authority or controls, and any affiliations, societies, organizations, associations, or agencies this church affiliates with to further the objectives stated in the Purpose Statement are not authoritative in matters of church practice or belief. (Acts 13:1-4; 15:19-31; 20:28; Rom. 16:1, 4; 1 Cor. 3:9, 16; 5:4-7, 13; 1 Pet. 5:1-4)',
				'4. We believe that the church is “the pillar and ground of the truth” (2 Tim 3:15) and that the local church is the most authoritative institution on earth and therefore responsible for displaying and preserving His truth before a lost and dying world.',
				'5. We recognize water baptism by immersion and the Lord’s Supper as the Scriptural ordinances of obedience for the church in this age.  (Matt. 28:19-20; Acts 2:41-42; 8:36-38; 1 Cor. 11:23-26)',
				'6. Though we do not believe that feet washing is an ordinance, we do believe that it is a practice designed to help the believer understand that all members of the Body of Christ are equal and should seek to love and serve one another as did our Lord.'
			]
		},
		{
			title: 'Separation',
			content: [
				'1. Ecclesiastical Separation: Separation of the church from the world is taught in scripture and is to be 	practiced by believers (2 Cor. 6:17; I Thess. 5:22). The church as a group of 	believers will not associate with churches which use worldly methods to promote 	the gospel. The church is to minister to the individuals in the world by giving out 	the gospel message through personal testimony, written material, evangelism, 	personal witnessing, church services and other methods, but it is not to use the 	worlds system of fulfilling sinful lusts through worldly entertainment, immorality, 	or other ungodly practices (James 4:4) in order to attract people to services. 	Therefore the church as a group, or as any sub-group, (i.e. youth, teens, ladies 	groups etc.) will not host, produce, nor participate in conferences, camps, 	fellowships, or other activities with churches or organizations which do not 	maintain a fundamental philosophy toward ministry and choose to use worldly 	attractions to draw people. Examples of these activities would include churches 	which host contemporary music concerts, or conferences which feature speakers 	that are neo-evangelical or charismatic in philosophy and practice, or meetings of 	an ecumenical nature with those which do not adhere to Bible principles and 	standards. ',
				'2. Personal Separation: We believe that believers should maintain a godly testimony and live in such a way that their lives do not bring reproach upon their Savior. God commands His people to separate from all religious apostasy, all worldly and sinful pleasures, practices, and associations, and to refrain from all immodest and immoderate appearances, piercings, and bodily markings. We stand against any and all worldly philosophies that seek to destroy or undermine the truth of Biblical Christianity by engaging in questionable activities which may not be expressly prohibited by name in scripture but certainly are prohibited or discouraged by Bible principles, such as nakedness,	immodest dress, viewing worldly and ungodly movies, listening to ungodly music, sexual 	immorality, the sale and use of tobacco in any form, drug abuse, pornography, etc. and other things which feed the flesh and hinder the believer’s walk in the Spirit.  We believe that Bible principles teach total abstinence from alcohol and as such believers should not be engaged in the sale or use of alcoholic beverages. Believers are to be free and separate from all oath-bound secret societies and partnerships with unbelievers. (Gal 5:16; Lev. 19:28; Rom. 12:1-2; 14:13; 1 Cor. 6:19-20; 2 Cor. 6:14-7:1; 2 Tim. 3:1-5; 1 John 2:15-17; 2 John 9-11)'
			]
		},
		{
			title: 'The Second Coming of Christ',
			content: [
				'We believe in that blessed hope, the personal, imminent return of Christ, Who will rapture His church prior to the seven-year tribulation period.  At the end of the Tribulation, Christ will personally and visibly return with His saints, to establish His earthly Messianic Kingdom, which will last for 1,000 years as promised to the nation of Israel.  (Ps. 89:3-4; Dan. 2:31-45; Zech. 14:4-11; 1 Thess. 1:10; 4:13-18; Titus 2:13; Rev. 3:10; 19:11-16; 20:1-7)'
			]
		},
		{
			title: 'The Eternal State',
			content: [
				'1. We believe in the bodily resurrection of all men, the saved to eternal life, and the unsaved to judgment and everlasting punishment.  (Matt. 25:46; John 5:28-29; 11:25-26; Rev. 20:5-6, 12-13)',
				'2. We believe that the souls of the redeemed are, at death, absent from the body and present with the Lord, where in conscious bliss they await the first resurrection, when spirit, soul, and body are reunited to be glorified forever with the Lord.  (Luke 23:43; 2 Cor. 5:8; Phil. 1:23; 3:21; 1 Thess. 4:16-17; Rev. 20:4-6) ',
				'3. We believe that the souls of unbelievers remain, after death, in conscious punishment and torment until the second resurrection, when with soul and body reunited, they shall appear at the Great White Throne Judgment, and shall be cast into the Lake of Fire, not to be annihilated, but to suffer everlasting conscious punishment and torment.  (Matt. 25:41-46; Mark 9:43-48; Luke 16:19-26; 2 Thess. 1:7-9; Jude 6-7; Rev. 20:11-15)'
			]
		},
		{
			title: 'The Personality of Satan',
			content: [
				'We believe that Satan is a personal being, created by God but who rebelled against the authority of God and became the author of sin and the chief instrument in the Fall of Man; that he is the open and declared enemy of God and man; and that he shall be eternally punished in the Lake of Fire forever and ever.  (Job 1:6-7; Isa. 14:12-17; Matt. 4:2-11; 25:41; Rev. 20:10)'
			]
		},
		{
			title: 'Creation',
			content: [
				'We believe that the Genesis account of creation is neither allegory, nor myth, but a literal, historical account of God’s creation of the universe in six, literal 24-hour days. We reject evolution, the Gap Theory, the Day-Age Theory, and Theistic Evolution as unscriptural theories of origin.  (Gen. 1-2; Ex. 20:11)'
			]
		},
		{
			title: 'Civil Government',
			content: [
				'We believe that God has ordained and created all authority consisting of three basic institutions:  1) the Home, 2) the Church, and 3) the State.  Every person is subject to these authorities, but all (including the authorities themselves) are answerable to God and governed by His Word.  God has given each institution specific Biblical responsibilities and balanced those responsibilities with the understanding that no institution has the right to infringe upon the other.  The home, the church, and the state are equal and sovereign in their respective Biblically assigned spheres of responsibility under God.  We believe that we must obey the state unless it requires us to act contrary to our faith at which time we must obey God rather than the state.  (Matt. 22:15-22; Acts 5:29; Rom. 13:1-7; Eph. 5:22-24; Titus 3:1-2; Heb. 13:17; 1 Pet. 2:13-14)'
			]
		},
		{
			title: 'Human Sexuality',
			content: [
				'1. We believe that God has commanded that no intimate sexual activity be engaged in outside of a marriage between one naturally-born man and one naturally-born woman.  We believe that any form of homosexuality, lesbianism, bisexuality, bestiality, incest, fornication, adultery, and pornography are sinful perversions of God’s gift of sex. We believe that God disapproves of and forbids any attempt to alter one’s gender by surgery or appearance.  (Gen. 2:24; Gen. 19:5, 13; Gen. 26:8-9; Lev. 18:1-30; Rom. 1: 26-29; 1 Cor. 5:1; 6:9; 1 Thess. 4:1-8; Heb. 13:4)',
				'2. We believe that the only Scriptural marriage is the joining of one naturally-born man and one naturally-born woman for life.  (Gen. 2:24; Rom. 7:2; 1 Cor. 7:10; Eph. 5:22-23)'
			]
		},
		{
			title: 'Family Relationships',
			content: [
				'1. We believe that men and women are spiritually equal in position before God but that God has ordained distinct and separate spiritual functions for men and women in the home and the church.  The husband is to be the leader of the home, and men are to be the leaders of the church.  Accordingly, only men are eligible for ordination by the church as pastors and deacons. (Gal. 3:28; Col. 3:18; 1 Tim. 2:8-15; 3:4-5, 12)',
				'2. We believe that God has ordained the family as the foundational institution of human society.  The husband is to love his wife as Christ loves the church.  The wife is to submit herself to the Scriptural leadership of her husband as the church submits to the headship of Christ.  Children are an heritage from the Lord.  Parents are responsible for teaching their children spiritual and moral values through consistent lifestyle example and appropriate discipline, including Scriptural corporal correction.  (Gen. 1:26-28; Ex. 20:12; Deut. 6:4-9; Ps. 127:3-5; Prov. 19:18; 22:15; 23:13-14; Mk. 10:6-12; 1 Cor. 7:1-16; Eph. 5:21-33; 6:1-4, Col. 3:18-21; Heb. 13:4; 1 Pet. 3:1-7)'
			]
		},
		{
			title: 'Divorce and Remarriage',
			content: [
				'We believe that God disapproves of and forbids divorce and intends marriage to last until one of the spouses dies. Divorce and remarriage is regarded as adultery except on the grounds of fornication. Although divorced and remarried persons or divorced persons may hold positions of service in the church and be greatly used of God for Christian service, they may not be considered for the offices of pastor or deacon.  (Mal. 2:14-17; Matt. 19:3-12; Rom. 7:1-3; 1 Tim. 3:2, 12; Titus 1:6) '
			]
		},
		{
			title: 'Abortion',
			content: [
				'We believe that human life begins at conception and that the unborn child is a living human being.  Abortion constitutes the unjustified, unexcused taking of unborn human life.  Abortion is murder.  We reject any teaching that abortions due to rape, incest, birth defects, gender selection, birth or population control, or the physical or mental well-being of the mother are acceptable. (Job 3:16; Ps. 51:5; 139:14-16; Isa. 44:24; 49:1, 5; Jer. 1:5; 20:15-18; Luke 1:44)'
			]
		},
		{
			title: 'Euthanasia',
			content: [
				'We believe that the direct taking of an innocent human life is a moral evil, regardless of the intention.  Life is a gift of God and must be respected from conception until natural death.  Discontinuing medical procedures that are extraordinary or disproportionate to the expected outcome can be a legitimate refusal of over-zealous treatment. (Ex. 20:13, 23:7; Matt. 5:21; Acts 17:28)'
			]
		},
		{
			title: 'Love',
			content: [
				'We believe that we should demonstrate love for others, not only toward fellow believers, but also toward those who are not believers, those who oppose us, and those who engage in sinful actions. We are to deal with those who oppose us graciously, gently, patiently, and humbly.  God forbids the stirring up of strife, the taking of revenge, or the threat or use of violence as a means of resolving personal conflict or obtaining personal justice. Although God commands us to abhor sinful actions, we are to love and pray for any person who engages in such sinful actions. (Lev. 19:18; Matt. 5:44-48; Luke 6:31; John 13:34-35; Rom. 12:9-10; 17-21; 13:8-10; Phil. 2:2-4; 2 Tim. 2:24-26; Titus 3:2; 1 John 3:17-18)'
			]
		},
		{
			title: 'Lawsuits Between Believers',
			content: [
				'We believe that Christians are prohibited from bringing civil lawsuits against other Christians or the church to resolve personal disputes.  We believe the local church possesses all the resources necessary to resolve personal disputes between members.  We do believe, however, that a Christian may seek compensation for injuries from another Christian’s insurance company as long as the claim is pursued without malice or slander.  (1 Cor. 6:1-8; Eph. 4:31-32; Matt. 18:15-17)'
			]
		},
		{
			title: 'Missions',
			content: [
				'We believe that God has given the church the great commission. It is to proclaim the Gospel to all nations so that there might be a great multitude from every nation, tribe, ethnic group, and language group who believe on the Lord Jesus Christ. As ambassadors of Christ, we must use all available means to go to the foreign nations and not wait for them to come to us.  (Matt. 28:19-20; Mark 16:15; Luke 24:46-48; John 20:21; Acts 1:8; 2 Cor. 5:20)'
			]
		},
		{
			title: 'Giving',
			content: [
				'We believe that every Christian, as a steward of that portion of God’s wealth entrusted to him, is obligated to financially support his local church.  We believe that God has established the tithe as a basis for giving, but that every Christian should also give other offerings sacrificially and cheerfully to the support of the ministries of the local church. We believe that a Christian relinquishes all rights to direct the use of his tithe or undesignated offerings once the gift has been made. (Gen. 14:20; Prov. 3:9-10; Acts 4:34-37; 1 Cor. 16:2; 2 Cor. 9:6-7; Gal. 6:6; Eph. 4:28; 1 Tim. 5:17-18; 1 John 3:17)'
			]
		}
	];
</script>

<div id="main" class="flex flex-col justify-center mt-40 grow min-h-80">
	<section
		id="our-pastor"
		class="data-[size=md]:scale-[0.8] data-[size=sm]:scale-75 w-screen relative ease-in-out flex transition-all duration-700 will-change-auto items-center flex-col space-y-40"
	>
		<div class="relative">
			<!-- GRADIENTS -->
			<div aria-hidden="true" class="grid absolute inset-0 grid-cols-2 -space-x-52 opacity-40">
				<div class="blur-[106px] h-56 bg-gradient-to-br from-theme-800 to-purple-400"></div>
				<div class="blur-[106px] h-32 bg-gradient-to-r from-cyan-400 to-sky-300"></div>
			</div>
			<div class="px-6 mx-auto max-w-7xl md:px-12 xl:px-6">
				<div class="relative">
					<div class="m-auto mt-6 space-y-6 md:w-8/12 lg:w-full">
						<h1 class="text-4xl font-black md:text-5xl">About Us</h1>
					</div>
				</div>
			</div>
		</div>
		<div class="px-6 mx-auto max-w-5xl md:px-12 lg:px-6 xl:px-0">
			<div class="relative ml-auto">
				<div class="gap-16 md:flex md:items-center">
					<div class="text-center sm:px-12 md:w-2/3 md:px-0 md:text-left lg:w-1/2">
						<h1 class="text-3xl font-bold text-center text-neutral-800 md:text-4xl">Our Pastor</h1>
						<div class="">
							<p class="mt-8 text-lg leading-loose text-neutral-700">
								Pastor Garner has served as the senior pastor of Emmanuel Baptist Church since 2019.
								He is originally from Arkansas, and came to NC when stationed at Ft. Bragg. While in
								the service he met his wife, Jeana, and was married in 1999.
							</p>
							<p class="mt-4 text-lg leading-loose text-neutral-700">
								Pastor Garner enjoys time with his family, especially on vacation in the mountains
								of Tennessee. He and his wife have two adult children and two children still in the
								home.
							</p>
						</div>
					</div>
					<div class="relative mt-20 md:mt-0 md:w-2/5 lg:w-3/5">
						<div class="-ml-0 md:-ml-6 lg:mr-0">
							<img
								class="object-cover object-left h-full rounded-xl dark:hidden"
								src="https://ik.imagekit.io/bip1v395ybp/Emmanuel%20Baptist%20Church/image_M8J7Q6rMd.jpg?updatedAt=1730959808912"
								alt="Garner Family"
								width="1628"
								height="1233"
							/>
							<img
								class="hidden object-cover object-left h-full dark:block"
								src="https://ik.imagekit.io/bip1v395ybp/Emmanuel%20Baptist%20Church/image_M8J7Q6rMd.jpg?updatedAt=1730959808912"
								alt="app screenshot"
								width="1628"
								height="1233"
							/>
						</div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<section
		id="ministries"
		class="data-[size=md]:scale-[0.8] data-[size=sm]:scale-75 w-screen relative ease-in-out flex transition-all duration-700 will-change-auto items-center flex-col"
	>
		<div class="flex-col items-center mx-auto mt-16 mb-0 w-full text-center md:w-1/2 lg:w-2/3">
			<h2 class="mt-8 text-3xl font-bold text-center text-neutral-800 md:text-4xl">
				Our Ministries
			</h2>
		</div>
		<div class="grid gap-6 p-4 mt-12 max-w-5xl sm:grid-cols-1 lg:grid-cols-2 md:mt-20">
			{#each ministryInformation as item}
				<div id={slugify(item.title)} class="space-y-6 w-full">
					<div
						class="overflow-hidden relative p-px bg-gradient-to-b from-neutral-200 to-white rounded-2xl"
					>
						{#if item.image}
							<div class="overflow-hidden relative rounded-t-xl">
								<img
									src={item.image}
									alt="art cover"
									loading="lazy"
									width="1000"
									height="667"
									class="object-cover object-top w-full h-64 transition duration-500 group-hover:scale-105"
								/>
							</div>
						{/if}
						<div
							class="flex relative flex-col gap-6 p-8 bg-neutral-100 rounded-2xl dark:bg-neutral-900"
						>
							<div class="flex gap-4">
								<div>
									<h3 class="text-xl font-bold text-neutral-700 md:text-2xl dark:text-white">
										{item.title}
									</h3>
								</div>
							</div>
							{#each item.description as paragraph}
								<p class="text-neutral-500 text-md">{paragraph}</p>
							{/each}
						</div>
					</div>
				</div>
			{/each}
		</div>
	</section>

	<section
		id="beliefs"
		class="data-[size=md]:scale-[0.8] data-[size=sm]:scale-75 w-screen relative ease-in-out flex transition-all duration-700 will-change-auto items-center flex-col mb-20"
	>
		<div class="flex-col items-center mx-auto my-8 w-full text-center md:my-16 md:w-1/2 lg:w-2/3">
			<h2 class="mt-8 text-3xl font-bold text-center text-neutral-800 md:text-4xl">Our Beliefs</h2>
		</div>
		<div class="flex flex-col items-center p-0 w-screen border-2 border-transparent">
			<Accordion class="p-6 w-full max-w-[800px] border-2 border-transparent">
				{#each beliefInformation as { title, content }}
					<AccordionItem class="p-6 focus:ring-0 focus:ring-transparent" open={false}>
						<span slot="header" class="pr-6 text-lg font-semibold md:text-2xl">{title}</span>
						{#each content as paragraph}
							<p class="px-6 py-3 mb-2 text-base leading-loose text-neutral-500">{paragraph}</p>
						{/each}
					</AccordionItem>
				{/each}
			</Accordion>
		</div>
	</section>
</div>
