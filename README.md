<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>医疗健康纪检通讯录</title>
     <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
     <style>
        /* 动态字体系统 */
        :root {
            --name-size: clamp(1.8rem, 6vw, 2.6rem);
            --base-size: clamp(1.2rem, 4vw, 1.6rem);
            --h3-size: clamp(1.8rem, 6vw, 2.4rem);
            --tel-size: clamp(1.6rem, 5vw, 2.2rem);
            --male-color: #4a90e2;
            --female-color: #ff6b81;
        }

        /* 折叠系统核心样式 */
        .contact-group {
            margin: 2vh 0;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }

        .group-header {
            padding: 3vh 4vw;
            background: #f8f9fa;
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
            min-height: 60px;
        }

        .group-header h3 {
            font-size: var(--h3-size) !important;
            margin: 0;
            color: #2c3e50;
        }

        .toggle-icon {
            font-size: var(--h3-size);
            transition: transform 0.3s;
        }

        .contact-list {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease-out;
            padding: 0 4vw;
        }

        .contact-group.active .contact-list {
            max-height: 2000px;
            padding: 2vh 4vw;
        }

        .contact-group.active .toggle-icon {
            transform: rotate(90deg);
        }

        .contact-name {
            font-size: var(--name-size) !important;
            font-weight: 500;
            margin-bottom: 0.3rem;
            color: #2c3e50;
        }

        /* 联系人卡片 */
        .contact-card {
            display: grid;
            grid-template-columns: 50px 1fr;
            gap: 4vw;
            padding: 3vh 4vw;
            margin: 1.5vh 0;
            background: #fff;
            border-radius: 8px;
            box-shadow: 0 1px 4px rgba(0,0,0,0.05);
        }

        .gender-icon {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
        }

        .male {
            background: var(--male-color); color: white;  }

        .female {
            background: var(--female-color); color: white; }

        .tel-link {
            grid-column: 1 / -1;
            font-size: var(--tel-size) !important;
            text-decoration: none;
            color: inherit;
            padding: 2vh 4vw;
            border-radius: 8px;
            background: #f8f9fa;
            text-align: center;
            transition: all 0.2s;
            padding: 12px;
            display: block;
            margin-top: 8px;
        }

        .tel-link:hover {
            background: #e9ecef;
        }

        /* 移动端优化 */
        @media (max-width: 480px) {
        .tel-link { 
            font-size: 1.4rem;
            padding: 12px; } /* 加大点击区域 */
        .group-header { min-height: 48px; } /* 更紧凑的标题 */
    }
            
            .contact-card {
                grid-template-columns: 40px 1fr;
            }
      }
    </style>
</head>
<body>
    <!-- 医疗公司（固定首位） -->
    <div class="contact-group">
        <div class="group-header">
            <h3>医疗公司</h3>
            <span class="toggle-icon"></span>
        </div>
        <div class="contact-list">
            <div class="contact-card">
                <div class="gender-icon male">♂</div>
                <div class="contact-info">
                <div class="contact-name">赵敏道</div>
        </div> 
           <a href="tel:15283998880" class="tel-link male-link">152-8399-8880</a>
            </div>
            <div class="contact-card">
                <div class="gender-icon male">♂</div>
                <div class="contact-info">
                <div class="contact-name">曾浩</div>
            </div>
                <a href="tel:18398783507" class="tel-link male-link">183-9878-3507</a>
            </div>
            <div class="contact-card">
                <div class="gender-icon female">♀</div>
                <div class="contact-info">
                <div class="contact-name">罗小琴</div>
            </div>
               <a href="tel:18908216777" class="tel-link female-link">189-0821-6777</a>
            </div>
            <div class="contact-card">
                <div class="gender-icon male">♂</div>
                <div class="contact-info">
                <div class="contact-name">王思锦</div>
           </div>
               <a href="tel:13550221030" class="tel-link male-link">135-5022-1030</a>
            </div>
        </div>
    </div>

    <!-- 按首字母排序的其他单位 -->
    <div class="contact-group">
        <div class="group-header">
            <h3>安庆一一六医院</h3>
            <span class="toggle-icon"></span>
        </div>
        <div class="contact-list">
            <div class="contact-card">
                <div class="gender-icon female">♀</div>
                <div class="contact-name">束寒玲</div>   
                <a href="tel:18905560259" class="tel-link female-link">189-0556-0259</a>
            </div>
            <div class="contact-card">
                <div class="gender-icon female">♀</div>
                <div class="contact-name">马琳</div>
                <a href="tel:13339066589" class="tel-link female-link">133-3906-6589</a>
            </div>
        </div>
    </div>

    <!-- 包头二九一医院 -->
    <div class="contact-group">
        <div class="group-header">
            <h3>包头二九一医院</h3>
            <span class="toggle-icon"></span>
        </div>
        <div class="contact-list">
            <div class="contact-card">
                <div class="gender-icon male">♂</div>
                <div class="contact-name">李保平</div>
                <a href="tel:15834012388" class="tel-link male-link">158-3401-2388</a>
            </div>
        </div>
    </div>

    <!-- 郴州一九八医院 -->
    <div class="contact-group">
        <div class="group-header">
            <h3>郴州一九八医院</h3>
            <span class="toggle-icon"></span>
        </div>
        <div class="contact-list">
            <div class="contact-card">
                <div class="gender-icon male">♂</div>
                <div class="contact-name">卢东辉</div>
             <a href="tel:18173583465" class="tel-link male-link">181-7358-3465</a>
            </div>
            <div class="contact-card">
                <div class="gender-icon female">♀</div>
                <div class="contact-name">何明月</div>
                <a href="tel:13762580842" class="tel-link female-link">137-6258-0842</a>
            </div>
        </div>
    </div>

<!-- 成都八一骨科医院 -->
<div class="contact-group">
    <div class="group-header">
        <h3>成都八一骨科医院</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon female">♀</div>
            <div class="contact-name">杜娟</div>
          <a href="tel:13709053668" class="tel-link female-link">137-0905-3668</a>
        </div>
        <div class="contact-card">
            <div class="gender-icon female">♀</div>
            <div class="contact-name">贺京羚</div>
            <a href="tel:13458610254" class="tel-link female-link">134-5861-0254</a>
        </div>
    </div>
</div>

<!-- 邯郸二八五医院 -->
<div class="contact-group">
    <div class="group-header">
        <h3>邯郸二八五医院</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">李江涛</div>
            <a href="tel:13832019691" class="tel-link male-link">138-3201-9691</a>
        </div>
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">龚志超</div>
            <a href="tel:17832291220" class="tel-link male-link">178-3229-1220</a>
        </div>
    </div>
</div>

<!-- 淮安八十二医院 -->
<div class="contact-group">
    <div class="group-header">
        <h3>淮安八十二医院</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">武晓军</div>
          <a href="tel:15189668199" class="tel-link male-link">151-8966-8199</a>
        </div>
        <div class="contact-card">
            <div class="gender-icon female">♀</div>
            <div class="contact-name">张 洁</div>
            <a href="tel:13770401537" class="tel-link female-link">137-7040-1537</a>
        </div>
        <div class="contact-card">
            <div class="gender-icon female">♀</div>
            <div class="contact-name">成宇琦</div>
           <a href="tel:15052682520" class="tel-link female-link">150-5268-2520</a>
        </div>
    </div>
</div>

<!-- 开封一五五医院 -->
<div class="contact-group">
    <div class="group-header">
        <h3>开封一五五医院</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon female">♀</div>
            <div class="contact-name">孟曼</div>
           <a href="tel:15037829297" class="tel-link female-link">150-3782-9297</a>
        </div>
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">陈文清</div>
         <a href="tel:17537883681" class="tel-link male-link">175-3788-3681</a>
        </div>
    </div>
</div>

<!-- 连云港一四九医院 -->
<div class="contact-group">
    <div class="group-header">
        <h3>连云港一四九医院</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">张云峰</div>
            <a href="tel:18961301789" class="tel-link male-link">189-6130-1789</a>
        </div>
        <div class="contact-card">
            <div class="gender-icon female">♀</div>
            <div class="contact-name">肖凯华</div>
            <a href="tel:18805134677" class="tel-link female-link">188-0513-4677</a>
        </div>
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">冯博</div>
            <a href="tel:15594269792" class="tel-link male-link">155-9426-9792</a>
        </div>
    </div>
</div>

<!-- 临夏七医院 -->
<div class="contact-group">
    <div class="group-header">
        <h3>临夏七医院</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">马涛</div>
            <a href="tel:18894011143" class="tel-link male-link">188-9401-1143</a>
        </div>
    </div>
</div>

<!-- 柳州一五八医院 -->
<div class="contact-group">
    <div class="group-header">
        <h3>柳州一五八医院</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon female">♀</div>
            <div class="contact-name">钱立蓉</div>
            <a href="tel:13637161556" class="tel-link female-link">136-3716-1556</a>
        </div>
        <div class="contact-card">
            <div class="gender-icon female">♀</div>
            <div class="contact-name">邹灵宇</div>
            <a href="tel:17799779723" class="tel-link female-link">177-9977-9723</a>
        </div>
    </div>
</div>

<!-- 马鞍山八十六医院 -->
<div class="contact-group">
    <div class="group-header">
        <h3>马鞍山八十六医院</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon female">♀</div>
            <div class="contact-name">吴彩艳</div>
            <a href="tel:13345558876" class="tel-link female-link">133-4555-8876</a>
        </div>
    </div>
</div>

<!-- 宁德四四二医院 -->
<div class="contact-group">
    <div class="group-header">
        <h3>宁德四四二医院</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon female">♀</div>
            <div class="contact-name">黄宁芳</div>
            <a href="tel:13799800834" class="tel-link female-link">137-9980-0834</a>
        </div>
    </div>
</div>

<!-- 莆田九十五医院 P -->
<div class="contact-group">
    <div class="group-header">
        <h3>莆田九十五医院</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">林德华</div>
            <a href="tel:18005941788" class="tel-link male-link">180-0594-1788</a>
        </div>
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">苗登田</div>
            <a href="tel:13559810950" class="tel-link male-link">135-5981-0950</a>
        </div>
        <div class="contact-card">
            <div class="gender-icon female">♀</div>
            <div class="contact-name">韩泽瑜</div>
            <a href="tel:13799670028" class="tel-link female-link">137-9967-0028</a>
        </div>
    </div>
</div>

<!-- 曲靖六十九医院 Q -->
<div class="contact-group">
    <div class="group-header">
        <h3>曲靖六十九医院</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon female">♀</div>
            <div class="contact-name">高桂芳</div>
            <a href="tel:15974523692" class="tel-link female-link">159-7452-3692</a>
        </div>
        <div class="contact-card">
            <div class="gender-icon female">♀</div>
            <div class="contact-name">赖恒卿</div>
            <a href="tel:18183933225" class="tel-link female-link">181-8393-3225</a>
        </div>
    </div>
</div>

<!-- 融通医药有限公司 R -->
<div class="contact-group">
    <div class="group-header">
        <h3>融通医药有限公司</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">袁小波</div>
            <a href="tel:18611629296" class="tel-link male-link">186-1162-9296</a>
        </div>
        <div class="contact-card">
            <div class="gender-icon female">♀</div>
            <div class="contact-name">王晶</div>
            <a href="tel:15528187185" class="tel-link female-link">155-2818-7185</a>
        </div>
    </div>
</div>

<!-- 上海四一一医院 S -->
<div class="contact-group">
    <div class="group-header">
        <h3>上海四一一医院</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">羊东</div>
            <a href="tel:18980666638" class="tel-link male-link">189-8066-6638</a>
        </div>
        <div class="contact-card">
            <div class="gender-icon female">♀</div>
            <div class="contact-name">汪薇</div>
            <a href="tel:18121259809" class="tel-link female-link">181-2125-9809</a>
        </div>
    </div>
</div>

<!-- 沈阳一二一医院 S -->
<div class="contact-group">
    <div class="group-header">
        <h3>沈阳一二一医院</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">杨明军</div>
            <a href="tel:13322445575" class="tel-link male-link">133-2244-5575</a>
        </div>
    </div>
</div>

<!-- 苏州一〇〇医院 S -->
<div class="contact-group">
    <div class="group-header">
        <h3>苏州一〇〇医院</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">胡腾</div>
            <a href="tel:18900568998" class="tel-link male-link">189-0056-8998</a>
        </div>
        <div class="contact-card">
            <div class="gender-icon female">♀</div>
            <div class="contact-name">陆漪</div>
            <a href="tel:13862169056" class="tel-link female-link">138-6216-9056</a>
        </div>
    </div>
</div>

<!-- 泰安八十八医院 T -->
<div class="contact-group">
    <div class="group-header">
        <h3>泰安八十八医院</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">孙士刚</div>
            <a href="tel:18553896058" class="tel-link male-link">185-5389-6058</a>
        </div>
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">房红伟</div>
            <a href="tel:13181819119" class="tel-link male-link">131-8181-9119</a>
        </div>
    </div>
</div>

<!-- 天津二七二医院 T -->
<div class="contact-group">
    <div class="group-header">
        <h3>天津二七二医院</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">王立超</div>
            <a href="tel:18132361181" class="tel-link male-link">181-3236-1181</a>
        </div>
        <div class="contact-card">
            <div class="gender-icon female">♀</div>
            <div class="contact-name">杨艳婷</div>
            <a href="tel:19922574186" class="tel-link female-link">199-2257-4186</a>
        </div>
    </div>
</div>

<!-- 新疆四七四医院 X -->
<div class="contact-group">
    <div class="group-header">
        <h3>新疆四七四医院</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">鲍祎凡</div>
            <a href="tel:13319804054" class="tel-link male-link">133-1980-4054</a>
        </div>
        <div class="contact-card">
            <div class="gender-icon female">♀</div>
            <div class="contact-name">陈雪琪</div>
            <a href="tel:18999786527" class="tel-link female-link">189-9978-6527</a>
        </div>
    </div>
</div>

<!-- 信阳一五四医院 X -->
<div class="contact-group">
    <div class="group-header">
        <h3>信阳一五四医院</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon female">♀</div>
            <div class="contact-name">万艳红</div>
            <a href="tel:13837629178" class="tel-link female-link">138-3762-9178</a>
        </div>
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">叶飞</div>
            <a href="tel:15565599858" class="tel-link male-link">155-6559-9858</a>
        </div>
        <div class="contact-card">
            <div class="gender-icon female">♀</div>
            <div class="contact-name">赵婧如</div>
            <a href="tel:13939732472" class="tel-link female-link">139-3973-2472</a>
        </div>
    </div>
</div>

<!-- 医健期刊公司 Y -->
<div class="contact-group">
    <div class="group-header">
        <h3>医健期刊公司</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon female">♀</div>
            <div class="contact-name">程锦</div>
            <a href="tel:13811262789" class="tel-link female-link">138-1126-2789</a>
        </div>
    </div>
</div>

<!-- 鹰潭一八四医院 Y -->
<div class="contact-group">
    <div class="group-header">
        <h3>鹰潭一八四医院</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">李强</div>
            <a href="tel:19007010575" class="tel-link male-link">190-0701-0575</a>
        </div>
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">吴鑫兴</div>
            <a href="tel:18007016031" class="tel-link male-link">180-0701-6031</a>
        </div>
    </div>
</div>

<!-- 镇江三五九医院 Z -->
<div class="contact-group">
    <div class="group-header">
        <h3>镇江三五九医院</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">冯秋阳</div>
            <a href="tel:15862999220" class="tel-link male-link">158-6299-9220</a>
        </div>
        <div class="contact-card">
            <div class="gender-icon female">♀</div>
            <div class="contact-name">刘佳</div>
            <a href="tel:15262926263" class="tel-link female-link">152-6292-6263</a>
        </div>
    </div>
</div>

<!-- 正定二五六医院 Z -->
<div class="contact-group">
    <div class="group-header">
        <h3>正定二五六医院</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">王宏宇</div>
            <a href="tel:15531128771" class="tel-link male-link">155-3112-8771</a>
        </div>
    </div>
</div>

<!-- 郑州四六〇医院 Z -->
<div class="contact-group">
    <div class="group-header">
        <h3>郑州四六〇医院</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">马辉</div>
            <a href="tel:13592485599" class="tel-link male-link">135-9248-5599</a>
        </div>
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">郭相鹏</div>
            <a href="tel:13140110491" class="tel-link male-link">131-4011-0491</a>
        </div>
    </div>
</div>

<!-- 淄博一四八医院 Z -->
<div class="contact-group">
    <div class="group-header">
        <h3>淄博一四八医院</h3>
        <span class="toggle-icon"></span>
    </div>
    <div class="contact-list">
        <div class="contact-card">
            <div class="gender-icon male">♂</div>
            <div class="contact-name">韩明明</div>
            <a href="tel:13678835280" class="tel-link male-link">136-7883-5280</a>
        </div>
        <div class="contact-card">
            <div class="gender-icon female">♀</div>
            <div class="contact-name">张晓旭</div>
            <a href="tel:17864355837" class="tel-link female-link">178-6435-5837</a>
        </div>
    </div>
</div>


<script>
    // 折叠控制
    document.querySelectorAll('.group-header').forEach(header => {
        header.addEventListener('click', () => {
            const group = header.parentElement;
            const isActive = group.classList.contains('active');
            
            document.querySelectorAll('.contact-group').forEach(g => {
                g.classList.remove('active');
            });

            if (!isActive) {
                group.classList.add('active');
            }
        });
    });

    
</script>
</body>
</html>
