<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aida - グループ</title>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@400;500;700;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
    <script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>
    <script src="https://www.gstatic.com/firebasejs/10.7.0/firebase-app-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/10.7.0/firebase-firestore-compat.js"></script>
    <style>
        :root { --primary: #6366f1; --secondary: #8b5cf6; --gradient: linear-gradient(135deg, #6366f1 0%, #8b5cf6 100%); --dark: #1e1b4b; --light: #f8fafc; --gray: #64748b; --success: #10b981; }
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: 'Noto Sans JP', sans-serif; background: var(--light); min-height: 100vh; }
        .header { background: var(--gradient); color: white; padding: 16px 20px; display: flex; justify-content: space-between; align-items: center; }
        .logo { font-size: 20px; font-weight: 900; }
        .header-link { color: white; text-decoration: none; font-size: 13px; opacity: 0.9; }
        .container { max-width: 600px; margin: 0 auto; padding: 20px; }
        .card { background: white; border-radius: 16px; padding: 24px; box-shadow: 0 4px 20px rgba(0,0,0,0.08); margin-bottom: 16px; }
        .card-title { font-size: 14px; font-weight: 700; color: var(--gray); margin-bottom: 16px; display: flex; align-items: center; gap: 8px; }
        .btn { width: 100%; padding: 14px; border: none; border-radius: 12px; font-size: 15px; font-weight: 700; cursor: pointer; transition: all 0.2s; }
        .btn-primary { background: var(--gradient); color: white; }
        .btn-primary:hover { box-shadow: 0 8px 25px rgba(99,102,241,0.3); }
        .btn-secondary { background: #f1f5f9; color: var(--dark); }
        .btn-success { background: var(--success); color: white; }
        .btn:disabled { opacity: 0.5; cursor: not-allowed; }
        .input { width: 100%; padding: 12px 14px; border: 2px solid #e2e8f0; border-radius: 10px; font-size: 15px; margin-bottom: 12px; }
        .input:focus { outline: none; border-color: var(--primary); }
        .member-list { margin-bottom: 16px; }
        .member-item { display: flex; align-items: center; gap: 12px; padding: 12px; background: #f8fafc; border-radius: 10px; margin-bottom: 8px; }
        .member-avatar { width: 36px; height: 36px; background: var(--gradient); color: white; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-weight: 700; font-size: 14px; }
        .member-info { flex: 1; }
        .member-name { font-weight: 600; font-size: 14px; }
        .member-station { font-size: 12px; color: var(--gray); }
        .suggestions { background: white; border: 1px solid #e2e8f0; border-radius: 10px; box-shadow: 0 10px 30px rgba(0,0,0,0.15); max-height: 200px; overflow-y: auto; display: none; position: absolute; left: 0; right: 0; z-index: 9999; }
        .suggestions.show { display: block; }
        .suggestion-item { padding: 10px 14px; cursor: pointer; border-bottom: 1px solid #f1f5f9; }
        .suggestion-item:hover { background: #f8fafc; }
        .suggestion-line { font-size: 11px; color: var(--gray); }
        .input-wrapper { position: relative; }
        .anywhere-btn { display: flex; align-items: center; gap: 8px; padding: 12px; background: #fef3c7; border: 2px solid #fcd34d; border-radius: 10px; cursor: pointer; margin-bottom: 12px; }
        .anywhere-btn.selected { background: #fde68a; }
        .anywhere-btn input { display: none; }
        .checkbox { width: 20px; height: 20px; border: 2px solid #f59e0b; border-radius: 4px; display: flex; align-items: center; justify-content: center; }
        .anywhere-btn.selected .checkbox { background: #f59e0b; color: white; }
        .share-box { background: #f1f5f9; border-radius: 10px; padding: 12px; display: flex; align-items: center; gap: 10px; margin-bottom: 16px; }
        .share-url { flex: 1; font-size: 13px; color: var(--dark); word-break: break-all; }
        .copy-btn { padding: 8px 16px; background: var(--primary); color: white; border: none; border-radius: 8px; font-size: 13px; font-weight: 600; cursor: pointer; }
        .hidden { display: none !important; }
    </style>
</head>
<body>
    <div class="header">
        <div class="logo">Aida</div>
        <a href="index.html" class="header-link">トップへ</a>
    </div>
    <div class="container">
        <!-- 新規作成画面 -->
        <div id="createView">
            <div class="card">
                <div class="card-title">🎉 新しいグループを作成</div>
                <input type="text" class="input" id="groupName" placeholder="グループ名（例: 忘年会2025）">
                <button class="btn btn-primary" onclick="createGroup()">グループを作成</button>
            </div>
        </div>

        <!-- グループ画面 -->
        <div id="groupView" class="hidden">
            <div class="card">
                <div class="card-title">📤 このURLを共有</div>
                <div class="share-box">
                    <div class="share-url" id="shareUrl"></div>
                    <button class="copy-btn" onclick="copyUrl()">コピー</button>
                </div>
                <button class="btn btn-success" onclick="shareToLine()">📱 LINEで送る</button>
            </div>

            <div class="card">
                <div class="card-title">👥 メンバー（<span id="memberCount">0</span>人）</div>
                <div class="member-list" id="memberList"></div>
                <button class="btn btn-primary" id="joinBtn" onclick="showJoinForm()">✋ 自分も参加する</button>
            </div>

            <!-- 参加フォーム -->
            <div class="card hidden" id="joinForm">
                <div class="card-title">🙋 参加情報を入力</div>
                <input type="text" class="input" id="nickname" placeholder="ニックネーム">
                <label class="anywhere-btn" id="anywhereBtn" onclick="toggleAnywhere()">
                    <div class="checkbox">✓</div>
                    <span>どこでもOK（駅を指定しない）</span>
                </label>
                <div class="input-wrapper" id="stationWrapper">
                    <input type="text" class="input" id="stationInput" placeholder="最寄り駅を入力..." oninput="searchStation()" onfocus="searchStation()">
                    <div class="suggestions" id="suggestions"></div>
                </div>
                <button class="btn btn-primary" onclick="joinGroup()">参加する</button>
            </div>

            <!-- 候補表示 -->
            <div class="card hidden" id="candidatesCard">
                <div class="card-title">🗳️ 候補に投票しよう</div>
                <div id="candidateList"></div>
            </div>
        </div>
    </div>
</body>
</html>

<style>
    .candidate-card { background: #f8fafc; border: 2px solid #e2e8f0; border-radius: 12px; padding: 14px; margin-bottom: 10px; cursor: pointer; transition: all 0.2s; }
    .candidate-card:hover { border-color: var(--primary); }
    .candidate-card.voted { border-color: var(--success); background: #ecfdf5; }
    .candidate-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 4px; }
    .candidate-name { font-size: 16px; font-weight: 700; }
    .candidate-badge { font-size: 11px; padding: 3px 8px; border-radius: 20px; font-weight: 600; }
    .badge-recommend { background: var(--gradient); color: white; }
    .badge-votes { background: #dbeafe; color: #1d4ed8; }
    .candidate-line { font-size: 12px; color: var(--gray); }
    .vote-bar { height: 6px; background: #e2e8f0; border-radius: 3px; margin-top: 8px; overflow: hidden; }
    .vote-bar-fill { height: 100%; background: var(--gradient); transition: width 0.3s; }
    .candidate-links { display: flex; gap: 6px; margin-top: 10px; flex-wrap: wrap; }
    .candidate-links a { font-size: 11px; color: var(--primary); text-decoration: none; padding: 4px 8px; background: white; border-radius: 6px; border: 1px solid #e2e8f0; }
    .map-card { border-radius: 16px; overflow: hidden; margin-bottom: 16px; }
    #map { height: 250px; width: 100%; }
    .status-badge { display: inline-block; padding: 4px 10px; border-radius: 20px; font-size: 12px; font-weight: 600; margin-bottom: 12px; }
    .status-waiting { background: #fef3c7; color: #b45309; }
    .status-ready { background: #d1fae5; color: #065f46; }
</style>
<script>
const firebaseConfig = {
    apiKey: "AIzaSyCxj6Qxk6PkL9WhbIQZh_wCwlhZBdY8MrQ",
    authDomain: "aida-f2eb3.firebaseapp.com",
    projectId: "aida-f2eb3",
    storageBucket: "aida-f2eb3.firebasestorage.app",
    messagingSenderId: "124876591098",
    appId: "1:124876591098:web:93bef3d94de8cf37799e43"
};
firebase.initializeApp(firebaseConfig);
const db = firebase.firestore();

let groupId = null;
let groupData = null;
let myMemberId = null;
let isAnywhere = false;
let selectedStation = null;

// URLからグループID取得
const urlParams = new URLSearchParams(window.location.search);
groupId = urlParams.get('g');

if (groupId) {
    document.getElementById('createView').classList.add('hidden');
    document.getElementById('groupView').classList.remove('hidden');
    loadGroup();
} else {
    document.getElementById('createView').classList.remove('hidden');
}

async function createGroup() {
    const name = document.getElementById('groupName').value.trim() || '新しいグループ';
    const docRef = await db.collection('groups').add({
        name: name,
        members: [],
        candidates: [],
        votes: {},
        createdAt: firebase.firestore.FieldValue.serverTimestamp()
    });
    groupId = docRef.id;
    window.history.pushState({}, '', `?g=${groupId}`);
    document.getElementById('createView').classList.add('hidden');
    document.getElementById('groupView').classList.remove('hidden');
    loadGroup();
}

// 本番URL
function getShareUrl() {
    // 本番環境（https://で始まる）ならそのまま使う
    if (window.location.protocol === 'https:') {
        return window.location.origin + '/app.html?g=' + groupId;
    }
    // ローカル環境の場合は本番URLを返す
    return 'https://top-bay-three.vercel.app/app.html?g=' + groupId;
}

async function loadGroup() {
    document.getElementById('shareUrl').textContent = getShareUrl();
    
    // リアルタイム監視
    db.collection('groups').doc(groupId).onSnapshot(doc => {
        if (doc.exists) {
            groupData = doc.data();
            renderMembers();
            checkAndShowCandidates();
        }
    });
}

function renderMembers() {
    const list = document.getElementById('memberList');
    const members = groupData.members || [];
    document.getElementById('memberCount').textContent = members.length;
    
    if (members.length === 0) {
        list.innerHTML = '<p style="color:#64748b;font-size:13px;text-align:center;padding:20px;">まだ誰も参加していません</p>';
    } else {
        list.innerHTML = members.map((m, i) => `
            <div class="member-item">
                <div class="member-avatar">${m.name.charAt(0)}</div>
                <div class="member-info">
                    <div class="member-name">${m.name}</div>
                    <div class="member-station">${m.anywhere ? '🌍 どこでもOK' : '🚉 ' + m.station + '駅'}</div>
                </div>
            </div>
        `).join('');
    }
    
    // 自分が参加済みかチェック
    const savedId = localStorage.getItem('aida_member_' + groupId);
    if (savedId && members.find(m => m.id === savedId)) {
        myMemberId = savedId;
        document.getElementById('joinBtn').classList.add('hidden');
        document.getElementById('joinForm').classList.add('hidden');
    }
}

function showJoinForm() {
    document.getElementById('joinForm').classList.remove('hidden');
    document.getElementById('joinBtn').classList.add('hidden');
}

function toggleAnywhere() {
    isAnywhere = !isAnywhere;
    document.getElementById('anywhereBtn').classList.toggle('selected', isAnywhere);
    document.getElementById('stationWrapper').classList.toggle('hidden', isAnywhere);
}

let searchTimeout = null;
function searchStation() {
    const query = document.getElementById('stationInput').value.trim();
    const suggestionsDiv = document.getElementById('suggestions');
    if (query.length < 1) { suggestionsDiv.classList.remove('show'); return; }
    clearTimeout(searchTimeout);
    searchTimeout = setTimeout(async () => {
        suggestionsDiv.innerHTML = '<div style="padding:10px;color:#64748b;">検索中...</div>';
        suggestionsDiv.classList.add('show');
        try {
            const res = await fetch(`https://express.heartrails.com/api/json?method=getStations&name=${encodeURIComponent(query)}`);
            const data = await res.json();
            if (data.response?.station) {
                const unique = [...new Map(data.response.station.map(s => [s.name + s.line, s])).values()];
                suggestionsDiv.innerHTML = unique.slice(0, 8).map(s => `
                    <div class="suggestion-item" onclick="selectStation('${s.name}',${s.y},${s.x},'${s.line}')">
                        <div>${s.name}駅</div>
                        <div class="suggestion-line">${s.line}（${s.prefecture}）</div>
                    </div>
                `).join('');
            } else { suggestionsDiv.innerHTML = '<div style="padding:10px;color:#64748b;">見つかりません</div>'; }
        } catch(e) { suggestionsDiv.innerHTML = '<div style="padding:10px;color:#ef4444;">エラー</div>'; }
    }, 300);
}

function selectStation(name, lat, lng, line) {
    selectedStation = { name, lat, lng, line };
    document.getElementById('stationInput').value = name;
    document.getElementById('suggestions').classList.remove('show');
}

document.addEventListener('click', e => {
    if (!e.target.closest('.input-wrapper')) document.getElementById('suggestions').classList.remove('show');
});

async function joinGroup() {
    const name = document.getElementById('nickname').value.trim();
    if (!name) { alert('ニックネームを入力してください'); return; }
    if (!isAnywhere && !selectedStation) { alert('駅を選択するか「どこでもOK」を選んでください'); return; }
    
    const memberId = 'member_' + Date.now();
    const member = {
        id: memberId,
        name: name,
        anywhere: isAnywhere,
        station: isAnywhere ? null : selectedStation.name,
        lat: isAnywhere ? null : selectedStation.lat,
        lng: isAnywhere ? null : selectedStation.lng
    };
    
    await db.collection('groups').doc(groupId).update({
        members: firebase.firestore.FieldValue.arrayUnion(member)
    });
    
    myMemberId = memberId;
    localStorage.setItem('aida_member_' + groupId, memberId);
    document.getElementById('joinForm').classList.add('hidden');
}

async function checkAndShowCandidates() {
    const members = groupData.members || [];
    const stationMembers = members.filter(m => !m.anywhere && m.lat && m.lng);
    
    if (stationMembers.length >= 2 && (!groupData.candidates || groupData.candidates.length === 0)) {
        await calculateCandidates(stationMembers);
    }
    
    if (groupData.candidates && groupData.candidates.length > 0) {
        renderCandidates();
    }
}

async function calculateCandidates(stationMembers) {
    const avgLat = stationMembers.reduce((s, m) => s + m.lat, 0) / stationMembers.length;
    const avgLng = stationMembers.reduce((s, m) => s + m.lng, 0) / stationMembers.length;
    
    try {
        const res = await fetch(`https://express.heartrails.com/api/json?method=getStations&x=${avgLng}&y=${avgLat}`);
        const data = await res.json();
        if (data.response?.station) {
            let candidates = data.response.station.slice(0, 8);
            candidates = [...new Map(candidates.map(c => [c.name, c])).values()].slice(0, 5);
            candidates = candidates.map(c => ({ name: c.name, lat: parseFloat(c.y), lng: parseFloat(c.x), line: c.line }));
            
            const votes = {};
            candidates.forEach(c => votes[c.name] = 0);
            
            await db.collection('groups').doc(groupId).update({ candidates, votes });
        }
    } catch(e) { console.error(e); }
}

function renderCandidates() {
    document.getElementById('candidatesCard').classList.remove('hidden');
    const candidates = groupData.candidates || [];
    const votes = groupData.votes || {};
    const totalVotes = Object.values(votes).reduce((a, b) => a + b, 0) || 1;
    const myVote = localStorage.getItem('aida_vote_' + groupId);
    
    const list = document.getElementById('candidateList');
    list.innerHTML = candidates.map((c, i) => {
        const voteCount = votes[c.name] || 0;
        const pct = Math.round((voteCount / totalVotes) * 100);
        const isVoted = myVote === c.name;
        return `
            <div class="candidate-card ${isVoted ? 'voted' : ''}" onclick="vote('${c.name}')">
                <div class="candidate-header">
                    <span class="candidate-name">${c.name}駅</span>
                    ${i === 0 ? '<span class="candidate-badge badge-recommend">おすすめ</span>' : ''}
                    ${voteCount > 0 ? `<span class="candidate-badge badge-votes">${voteCount}票</span>` : ''}
                </div>
                <div class="candidate-line">${c.line || ''}</div>
                ${totalVotes > 1 ? `<div class="vote-bar"><div class="vote-bar-fill" style="width:${pct}%"></div></div>` : ''}
                <div class="candidate-links">
                    <a href="https://tabelog.com/rstLst/?vs=1&sa=${encodeURIComponent(c.name + '駅')}&sk=${encodeURIComponent(c.name)}" target="_blank">🍺 食べログで${c.name}駅周辺を探す</a>
                    <a href="https://www.hotpepper.jp/CSP/psh/freeword_search/freeword_search.do?FWT=${encodeURIComponent(c.name + '駅')}" target="_blank">🍴 ホットペッパー</a>
                    <a href="https://www.google.com/maps/search/居酒屋/@${c.lat},${c.lng},16z" target="_blank">🗺️ Googleマップ</a>
                </div>
            </div>
        `;
    }).join('');
}

async function vote(stationName) {
    const myVote = localStorage.getItem('aida_vote_' + groupId);
    if (myVote) { alert('すでに投票済みです'); return; }
    
    const votes = { ...groupData.votes };
    votes[stationName] = (votes[stationName] || 0) + 1;
    
    await db.collection('groups').doc(groupId).update({ votes });
    localStorage.setItem('aida_vote_' + groupId, stationName);
}

function copyUrl() {
    navigator.clipboard.writeText(getShareUrl());
    alert('URLをコピーしました！');
}

function shareToLine() {
    const name = groupData?.name || 'グループ';
    const text = `【${name}】の待ち合わせ場所を決めよう！\n\nAidaで中間地点を探して投票👇`;
    window.open(`https://line.me/R/msg/text/?${encodeURIComponent(text + '\n' + getShareUrl())}`, '_blank');
}
</script>
