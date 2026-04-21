import { useState, useEffect, useCallback, useRef } from "react";

// ── MASCOT SVG ──────────────────────────────────────────────
const Mascot = ({ size = 90 }) => (
  <svg width={size} height={size * 1.18} viewBox="0 0 100 118" fill="none">
    <ellipse cx="50" cy="38" rx="24" ry="24" fill="#111"/>
    <ellipse cx="35" cy="50" rx="17" ry="16" fill="#111"/>
    <ellipse cx="65" cy="50" rx="17" ry="16" fill="#111"/>
    <ellipse cx="50" cy="56" rx="17" ry="15" fill="#111"/>
    <ellipse cx="50" cy="46" rx="21" ry="21" fill="#111"/>
    <ellipse cx="50" cy="46" rx="29" ry="29" fill="none" stroke="#25B874" strokeWidth="1.2" strokeDasharray="3 5" opacity=".3"/>
    <ellipse cx="42" cy="42" rx="8.5" ry="6.5" fill="white"/>
    <ellipse cx="58" cy="42" rx="8.5" ry="6.5" fill="white"/>
    <ellipse cx="43" cy="43" rx="5.5" ry="5" fill="#111"/>
    <ellipse cx="59" cy="43" rx="5.5" ry="5" fill="#111"/>
    <circle cx="44.5" cy="41" r="2" fill="white"/>
    <circle cx="60.5" cy="41" r="2" fill="white"/>
    <path d="M35 35 Q42 32 49 35" stroke="#111" strokeWidth="2.2" strokeLinecap="round" fill="none"/>
    <path d="M51 35 Q58 32 65 35" stroke="#111" strokeWidth="2.2" strokeLinecap="round" fill="none"/>
    <rect x="36" y="68" width="12" height="26" rx="6" fill="#111"/>
    <rect x="52" y="68" width="12" height="26" rx="6" fill="#111"/>
    <ellipse cx="42" cy="94" rx="11" ry="6.5" fill="#111"/>
    <ellipse cx="58" cy="94" rx="11" ry="6.5" fill="#111"/>
    <text x="50" y="112" textAnchor="middle" fontFamily="monospace" fontSize="9" fill="#25B874" letterSpacing="2.5" fontWeight="700">SOON</text>
  </svg>
);

// ── DEFAULTS ────────────────────────────────────────────────
const uid = () => 'x' + Math.random().toString(36).slice(2, 8);
const num = s => Number(String(s || '').replace(/,/g, '')) || 0;
const fmt = n => n ? n.toLocaleString() : '—';

const DEFAULTS = {
  months: [
    { id: 'm1', label: 'เมษายน 2569', tasks: [
      { id: 't1', name: 'รอแบบ Final', sub: 'ขั้นตอนแรก — ต้องได้แบบก่อนทุกอย่าง', tag: 'กำลังดำเนินการ', status: 'active' },
      { id: 't2', name: 'แบบเรนเดอร์จาก Final', sub: 'เรนเดอร์ Final เพื่อประกอบตัดสินใจ', tag: 'ภายในเม.ย. 69', status: 'active' },
      { id: 't3', name: 'หาช่างทำร้าน — เปรียบเทียบ', sub: 'ไม่เกินกลางพฤษภาคม', tag: 'เม.ย.–กลางพ.ค.', status: 'active' },
      { id: 't4', name: 'ทำ 3D รูปหน้าร้าน Soon Siam', sub: 'ประกอบการนำเสนอและขออนุญาตจุฬาฯ', tag: 'ระหว่างดำเนินการ', status: 'pending' },
    ]},
    { id: 'm2', label: 'พฤษภาคม 2569', tasks: [
      { id: 't5', name: 'ส่งแบบจุฬาฯ', sub: 'ต้องมีแบบ Final + 3D พร้อมก่อน', tag: 'ต้นพ.ค.', status: 'critical' },
      { id: 't6', name: 'นัดคุยกับจุฬาฯ', sub: 'ประชุมขออนุมัติ', tag: 'ต้นพ.ค.', status: 'critical' },
    ]},
    { id: 'm3', label: 'มิถุนายน 2569', tasks: [
      { id: 't7', name: 'เริ่มรีโนเวทร้าน', sub: 'ทุกอย่างต้องเรียบร้อยก่อนลงมือ', tag: 'ต้นมิ.ย.', status: 'done' },
    ]},
  ],
  critical: [
    'แบบ Final ต้องได้ก่อน — ถ้าช้า ทุกขั้นตอนหลังล่าช้าตาม',
    'จุฬาฯ ต้องอนุมัติก่อนมิถุนายน',
    'ช่างต้องนัดล็อกวันได้ก่อนกลางพฤษภาคม',
    'งบประมาณต้องอนุมัติก่อนเริ่มงาน',
  ],
  vendors: [
    { id: 'v1', type: 'design', name: 'สถาปนิก / ดีไซเนอร์', sub: 'ออกแบบ Final + เรนเดอร์ร้าน', contact: '', budget: '', skills: 'วาดแบบ, เรนเดอร์ 3D, ทำ BOQ', status: 'inprog', selected: true, imgs: [] },
    { id: 'v2', type: '3d', name: 'นักทำ 3D หน้าร้าน', sub: 'ทำ 3D รูปหน้าร้าน Soon Siam', contact: '', budget: '', skills: '3D modeling, visualization', status: 'confirm', selected: false, imgs: [] },
    { id: 'v3', type: 'contractor', name: 'ช่างรีโนเวท', sub: 'งานก่อสร้างและตกแต่งภายใน', contact: '', budget: '', skills: 'งานผนัง, พื้น, ไฟฟ้า, ประปา', status: 'confirm', selected: false, imgs: [] },
  ],
  budget: [
    { id: 'bs1', title: 'ค่าออกแบบ (Design Fee)', rows: [
      { id: 'br1', name: 'ค่าแบบ Final + เรนเดอร์', amt: '', status: 'not-yet' },
      { id: 'br2', name: 'ค่า 3D หน้าร้าน', amt: '', status: 'not-yet' },
    ]},
    { id: 'bs2', title: 'ค่าก่อสร้าง (Construction)', rows: [
      { id: 'br3', name: 'ค่าช่างทำร้าน', amt: '', status: 'not-yet' },
      { id: 'br4', name: 'วัสดุและอุปกรณ์', amt: '', status: 'not-yet' },
      { id: 'br5', name: 'ค่าไฟฟ้า / ประปา', amt: '', status: 'not-yet' },
    ]},
    { id: 'bs3', title: 'ค่าจุฬาฯ / ค่าธรรมเนียม', rows: [
      { id: 'br6', name: 'ค่าธรรมเนียมขออนุญาต', amt: '', status: 'not-yet' },
      { id: 'br7', name: 'ค่าจ้างยื่นเอกสาร', amt: '', status: 'not-yet' },
    ]},
    { id: 'bs4', title: 'งบสำรอง (Contingency)', rows: [
      { id: 'br8', name: 'งบสำรองเผื่อบาน', amt: '', status: 'not-yet' },
    ]},
  ],
};

const SC = ['pending', 'active', 'critical', 'done'];
const SI = { pending: '○', active: '◑', critical: '!', done: '✓' };
const VS_LABEL = { confirm: 'รอยืนยัน', inprog: 'กำลังดำเนินการ', review: 'รอตรวจงาน', pay: 'รอชำระเงิน', done: 'เสร็จสิ้น', cancel: 'ยกเลิก' };
const VS_COLOR = {
  confirm: { bg: '#FEF7E0', border: '#FAC775', color: '#C47B00' },
  inprog:  { bg: '#EBF4FF', border: '#90CAF9', color: '#1A6FBB' },
  review:  { bg: '#F0ECFE', border: '#C5B8F9', color: '#4A35A8' },
  pay:     { bg: '#FEF7E0', border: '#EF9F27', color: '#C47B00' },
  done:    { bg: '#E8F7F1', border: '#81C995', color: '#0F5238' },
  cancel:  { bg: '#FEF0EE', border: '#FFAB9A', color: '#D13B2A' },
};

const S_COLOR = {
  active:   { dot: '#1A6FBB', btn: { bg: '#EBF4FF', border: '#90CAF9' } },
  critical: { dot: '#D13B2A', btn: { bg: '#FEF0EE', border: '#FFAB9A' } },
  done:     { dot: '#1A7A52', btn: { bg: '#E8F7F1', border: '#81C995' } },
  pending:  { dot: '#CCCCCC', btn: { bg: '#F5F5F5', border: '#E0E0E0' } },
};

// ── STYLES (inline) ─────────────────────────────────────────
const g = { main: '#1A7A52', light: '#25B874', dark: '#0F5238' };
const bk = '#0D0D0D';

// ══════════════════════════════════════════════════════════
export default function App() {
  const [data, setData] = useState(null);
  const [page, setPage] = useState('overview');
  const [saveState, setSaveState] = useState('loading');
  const [toast, setToast] = useState('');
  const [lb, setLb] = useState(null);
  const saveTimer = useRef(null);
  const pollTimer = useRef(null);

  // ── SHARED STORAGE ────────────────────────────────────────
  const STORAGE_KEY = 'soonsiam_shared_v1';

  const loadData = useCallback(async () => {
    try {
      const res = await window.storage.get(STORAGE_KEY, true); // shared=true
      if (res && res.value) {
        setData(JSON.parse(res.value));
      } else {
        setData(JSON.parse(JSON.stringify(DEFAULTS)));
      }
      setSaveState('ok');
    } catch {
      setData(JSON.parse(JSON.stringify(DEFAULTS)));
      setSaveState('ok');
    }
  }, []);

  // Poll every 8s for updates from other users
  const startPolling = useCallback(() => {
    pollTimer.current = setInterval(async () => {
      try {
        const res = await window.storage.get(STORAGE_KEY, true);
        if (res && res.value) {
          const fresh = JSON.parse(res.value);
          setData(prev => {
            // only update if different (avoid stomping mid-edit)
            if (JSON.stringify(prev) !== JSON.stringify(fresh)) return fresh;
            return prev;
          });
        }
      } catch {}
    }, 8000);
  }, []);

  useEffect(() => {
    loadData();
    startPolling();
    return () => clearInterval(pollTimer.current);
  }, []);

  const save = useCallback(async (newData) => {
    setSaveState('saving');
    clearTimeout(saveTimer.current);
    saveTimer.current = setTimeout(async () => {
      try {
        await window.storage.set(STORAGE_KEY, JSON.stringify(newData), true); // shared=true
        setSaveState('ok');
        showToast('บันทึกแล้ว — ทุกคนเห็นแล้ว');
      } catch {
        setSaveState('err');
      }
    }, 600);
  }, []);

  const update = useCallback((updater) => {
    setData(prev => {
      const next = updater(JSON.parse(JSON.stringify(prev)));
      save(next);
      return next;
    });
  }, [save]);

  const showToast = (m) => {
    setToast(m);
    setTimeout(() => setToast(''), 2500);
  };

  if (!data) return (
    <div style={{ display: 'flex', flexDirection: 'column', alignItems: 'center', justifyContent: 'center', height: 400, gap: 16 }}>
      <div style={{ animation: 'spin 1s linear infinite' }}>
        <Mascot size={70} />
      </div>
      <div style={{ fontSize: 14, color: '#888' }}>กำลังโหลด...</div>
    </div>
  );

  const pages = ['overview', 'timeline', 'vendors', 'budget'];
  const pageLabels = ['ภาพรวม', 'ไทม์ไลน์', 'ผู้รับเหมา', 'งบประมาณ'];

  return (
    <div style={{ fontFamily: "'Kanit', 'Noto Sans Thai', sans-serif", background: '#F7F8F6', minHeight: '100vh' }}>
      <style>{`
        @import url('https://fonts.googleapis.com/css2?family=Kanit:wght@300;400;500;600;700;900&family=Space+Mono:wght@400;700&display=swap');
        * { box-sizing: border-box; }
        input, select, button { font-family: inherit; }
        input:focus, select:focus { outline: none; }
        .task-del { opacity: 0; } .task-row:hover .task-del { opacity: 1; }
        .month-del { opacity: 0; } .month-hdr:hover .month-del { opacity: 1; }
        .crit-del { opacity: 0; } .crit-row:hover .crit-del { opacity: 1; }
        .vendor-del { opacity: 0; } .vc-card:hover .vendor-del { opacity: 1; }
        @keyframes float { 0%,100%{transform:translateY(0)} 50%{transform:translateY(-8px)} }
        @keyframes spin { to{transform:rotate(360deg)} }
        @keyframes fadein { from{opacity:0;transform:translateY(8px)} to{opacity:1;transform:translateY(0)} }
      `}</style>

      {/* NAV */}
      <div style={{ background: bk, position: 'sticky', top: 0, zIndex: 100, padding: '0 16px', display: 'flex', alignItems: 'center', justifyContent: 'space-between', height: 52, borderBottom: '1px solid #252525' }}>
        <div style={{ display: 'flex', alignItems: 'center', gap: 8, color: 'white', fontWeight: 700, fontSize: 14, letterSpacing: '.05em', flexShrink: 0 }}>
          <Mascot size={26} />
          SOON<span style={{ color: g.light }}>SIAM</span>
        </div>
        <div style={{ display: 'flex', gap: 2, overflowX: 'auto' }}>
          {pages.map((p, i) => (
            <button key={p} onClick={() => setPage(p)} style={{
              padding: '5px 11px', borderRadius: 6, fontSize: 12, border: 'none',
              cursor: 'pointer', whiteSpace: 'nowrap', transition: 'all .15s',
              background: page === p ? g.main : 'transparent',
              color: page === p ? 'white' : '#888',
            }}>{pageLabels[i]}</button>
          ))}
        </div>
        <div style={{ display: 'flex', alignItems: 'center', gap: 6, fontSize: 11, color: '#888', fontFamily: 'monospace', flexShrink: 0 }}>
          <div style={{ width: 7, height: 7, borderRadius: '50%', background: saveState === 'saving' ? '#C47B00' : saveState === 'err' ? '#D13B2A' : g.light, animation: saveState === 'saving' ? 'blink .7s infinite' : 'none' }} />
          <span>{saveState === 'saving' ? 'กำลังซิงค์...' : saveState === 'err' ? 'ซิงค์ไม่สำเร็จ' : 'ซิงค์แล้ว'}</span>
        </div>
      </div>

      {/* LIGHTBOX */}
      {lb && (
        <div onClick={() => setLb(null)} style={{ position: 'fixed', inset: 0, background: 'rgba(0,0,0,.93)', zIndex: 9999, display: 'flex', alignItems: 'center', justifyContent: 'center' }}>
          <button onClick={() => setLb(null)} style={{ position: 'absolute', top: 18, right: 22, background: 'none', border: 'none', color: 'white', fontSize: 26, cursor: 'pointer' }}>✕</button>
          <img src={lb} alt="" style={{ maxWidth: '90vw', maxHeight: '85vh', borderRadius: 14, objectFit: 'contain' }} />
        </div>
      )}

      {/* TOAST */}
      {toast && (
        <div style={{ position: 'fixed', bottom: 20, right: 20, zIndex: 999, background: bk, color: 'white', padding: '10px 18px', borderRadius: 9, fontSize: 13, borderLeft: `3px solid ${g.light}`, animation: 'fadein .3s ease' }}>
          {toast}
        </div>
      )}

      <div style={{ maxWidth: 900, margin: '0 auto', padding: '22px 14px 80px' }}>

        {/* ═══ OVERVIEW ═══════════════════════════════════ */}
        {page === 'overview' && <Overview data={data} />}

        {/* ═══ TIMELINE ═══════════════════════════════════ */}
        {page === 'timeline' && <Timeline data={data} update={update} />}

        {/* ═══ VENDORS ════════════════════════════════════ */}
        {page === 'vendors' && <Vendors data={data} update={update} setLb={setLb} showToast={showToast} />}

        {/* ═══ BUDGET ═════════════════════════════════════ */}
        {page === 'budget' && <Budget data={data} update={update} />}

      </div>
    </div>
  );
}

// ══ OVERVIEW ═══════════════════════════════════════════════
function Overview({ data }) {
  let tot = 0, done = 0, grand = 0, paid = 0;
  data.months.forEach(m => m.tasks.forEach(t => { tot++; if (t.status === 'done') done++; }));
  data.budget.forEach(s => s.rows.forEach(r => { const a = num(r.amt); grand += a; if (r.status === 'paid') paid += a; }));

  const stats = [
    { num: tot, label: 'งานทั้งหมด' },
    { num: done, label: 'เสร็จแล้ว' },
    { num: data.vendors.length, label: 'ผู้รับเหมา' },
    { num: grand ? grand.toLocaleString() : '—', label: 'งบรวม (฿)', sub: paid ? 'จ่ายแล้ว ' + paid.toLocaleString() : '' },
  ];

  return (
    <div>
      {/* Hero */}
      <div style={{ background: bk, borderRadius: 14, padding: 28, marginBottom: 18, display: 'flex', alignItems: 'center', gap: 20, position: 'relative', overflow: 'hidden' }}>
        <div style={{ position: 'absolute', inset: 0, background: 'radial-gradient(ellipse 55% 110% at 100% 50%, rgba(26,120,82,.2) 0%, transparent 65%)' }} />
        <div style={{ flex: 1, position: 'relative', zIndex: 1 }}>
          <div style={{ fontFamily: 'Space Mono, monospace', fontSize: 10, letterSpacing: '.18em', color: g.light, marginBottom: 8 }}>SOON SIAM SQUARE — RENOVATION HQ</div>
          <h1 style={{ fontSize: 'clamp(22px,4vw,34px)', fontWeight: 900, color: 'white', lineHeight: 1.1, letterSpacing: '-.02em', margin: 0 }}>
            แผน<span style={{ color: g.light }}>รีโนเวท</span><br />ร้าน Soon Siam
          </h1>
          <p style={{ fontSize: 13, color: '#888', marginTop: 6, fontWeight: 300 }}>ข้อมูลซิงค์ร่วมกัน — ทุกคนเห็นการอัปเดตพร้อมกัน</p>
          <div style={{ display: 'inline-flex', alignItems: 'center', marginTop: 12, background: '#0F3D28', border: '1px solid #1A5C3A', color: g.light, fontFamily: 'Space Mono, monospace', fontSize: 10, padding: '5px 13px', borderRadius: 99, letterSpacing: '.08em' }}>
            TARGET: เริ่มรีโนเวท มิถุนายน 2569
          </div>
        </div>
        <div style={{ animation: 'float 4s ease-in-out infinite', flexShrink: 0 }}>
          <Mascot size={90} />
        </div>
      </div>

      {/* Stats */}
      <div style={{ display: 'grid', gridTemplateColumns: 'repeat(4,1fr)', gap: 10, marginBottom: 18 }}>
        {stats.map((s, i) => (
          <div key={i} style={{ background: 'white', border: '1px solid #EDEDE9', borderRadius: 9, padding: 14, textAlign: 'center' }}>
            <div style={{ fontSize: 28, fontWeight: 700, color: g.main, lineHeight: 1 }}>{s.num}</div>
            <div style={{ fontSize: 12, color: '#888', marginTop: 4 }}>{s.label}</div>
            {s.sub && <div style={{ fontSize: 10, fontFamily: 'monospace', color: '#555', marginTop: 2 }}>{s.sub}</div>}
          </div>
        ))}
      </div>

      {/* Budget bars */}
      <div style={{ background: 'white', border: '1px solid #EDEDE9', borderRadius: 14, padding: '18px 22px', marginBottom: 18 }}>
        <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center', marginBottom: 14 }}>
          <div style={{ fontSize: 14, fontWeight: 600 }}>สัดส่วนงบประมาณ</div>
          <div style={{ fontSize: 12, color: '#888', fontFamily: 'monospace' }}>รวม <span style={{ color: g.main, fontWeight: 700 }}>{grand.toLocaleString()}</span> ฿</div>
        </div>
        {data.budget.map(s => {
          const st = s.rows.reduce((a, r) => a + num(r.amt), 0);
          if (!st) return null;
          const pct = grand ? Math.round(st / grand * 100) : 0;
          return (
            <div key={s.id} style={{ display: 'flex', alignItems: 'center', gap: 10, marginBottom: 8 }}>
              <div style={{ fontSize: 12, width: 150, flexShrink: 0, color: '#555' }}>{s.title.split('(')[0].trim()}</div>
              <div style={{ flex: 1, height: 7, background: '#EDEDE9', borderRadius: 99, overflow: 'hidden' }}>
                <div style={{ height: '100%', borderRadius: 99, background: g.main, width: pct + '%', transition: 'width .6s' }} />
              </div>
              <div style={{ fontSize: 11, fontFamily: 'monospace', color: '#555', minWidth: 80, textAlign: 'right' }}>{fmt(st)} ฿</div>
            </div>
          );
        })}
      </div>

      {/* Mini timeline */}
      <div style={{ background: 'white', border: '1px solid #EDEDE9', borderRadius: 14, padding: '18px 22px' }}>
        <div style={{ fontFamily: 'Space Mono, monospace', fontSize: 10, letterSpacing: '.15em', color: '#888', textTransform: 'uppercase', marginBottom: 14 }}>ไทม์ไลน์</div>
        <div style={{ display: 'flex', gap: 0, overflowX: 'auto', paddingBottom: 4 }}>
          {data.months.map((m, mi) => (
            <div key={m.id} style={{ minWidth: 160, flex: 1, position: 'relative', paddingRight: 14, paddingBottom: 10, borderRight: mi < data.months.length - 1 ? '1px solid #EDEDE9' : 'none' }}>
              <div style={{ fontSize: 12, fontWeight: 600, color: g.main, marginBottom: 8, display: 'flex', alignItems: 'center', gap: 6 }}>
                <div style={{ width: 7, height: 7, borderRadius: '50%', background: g.main }} />{m.label}
              </div>
              {m.tasks.map(t => {
                const chipColor = { active: { bg: '#EBF4FF', c: '#1A6FBB', b: '#90CAF9' }, critical: { bg: '#FEF0EE', c: '#D13B2A', b: '#FFAB9A' }, done: { bg: '#E8F7F1', c: '#0F5238', b: '#81C995' }, pending: { bg: '#EDEDE9', c: '#555', b: '#EDEDE9' } }[t.status];
                return (
                  <div key={t.id} style={{ display: 'inline-block', fontSize: 10, padding: '2px 7px', borderRadius: 99, marginBottom: 3, border: `1px solid ${chipColor.b}`, background: chipColor.bg, color: chipColor.c, marginRight: 3 }}>
                    {t.name.length > 14 ? t.name.slice(0, 13) + '…' : t.name}
                  </div>
                );
              })}
            </div>
          ))}
        </div>
      </div>
    </div>
  );
}

// ══ TIMELINE ════════════════════════════════════════════════
function Timeline({ data, update }) {
  const cycleStatus = (mid, tid) => update(d => {
    const t = d.months.find(x => x.id === mid).tasks.find(x => x.id === tid);
    t.status = SC[(SC.indexOf(t.status) + 1) % SC.length];
    return d;
  });

  return (
    <div>
      {data.months.map(m => (
        <div key={m.id} style={{ marginBottom: 24 }}>
          <div className="month-hdr" style={{ display: 'flex', alignItems: 'center', gap: 10, marginBottom: 10 }}>
            <div style={{ width: 10, height: 10, borderRadius: '50%', background: g.main, flexShrink: 0 }} />
            <input value={m.label} onChange={e => update(d => { d.months.find(x => x.id === m.id).label = e.target.value; return d; })}
              style={{ fontSize: 16, fontWeight: 600, background: 'none', border: 'none', borderBottom: '1.5px dashed transparent', flex: 1, padding: '2px 4px', cursor: 'text' }}
              onFocus={e => e.target.style.borderBottomColor = g.main}
              onBlur={e => e.target.style.borderBottomColor = 'transparent'} />
            <button className="month-del" onClick={() => { if (confirm('ลบเดือนนี้?')) update(d => { d.months = d.months.filter(x => x.id !== m.id); return d; }); }}
              style={{ background: 'none', border: 'none', cursor: 'pointer', fontSize: 12, color: '#888', padding: '4px 8px', borderRadius: 6 }}>ลบเดือน</button>
          </div>

          {/* Tasks */}
          <div style={{ paddingLeft: 20, borderLeft: '2px solid #EDEDE9', marginLeft: 4 }}>
            {m.tasks.map(t => {
              const sc = S_COLOR[t.status] || S_COLOR.pending;
              return (
                <div key={t.id} className="task-row" style={{ background: 'white', border: '1px solid #EDEDE9', borderRadius: 9, padding: '11px 14px', marginBottom: 7, display: 'flex', gap: 10, alignItems: 'flex-start', position: 'relative', transition: 'border-color .2s' }}
                  onMouseEnter={e => e.currentTarget.style.borderColor = '#C5E8D8'}
                  onMouseLeave={e => e.currentTarget.style.borderColor = '#EDEDE9'}>
                  <div style={{ position: 'absolute', left: -13, top: '50%', transform: 'translateY(-50%)', width: 9, height: 9, borderRadius: '50%', border: '2px solid #F7F8F6', background: sc.dot }} />
                  <button onClick={() => cycleStatus(m.id, t.id)} style={{ width: 26, height: 26, borderRadius: 7, border: `1.5px solid ${sc.btn.border}`, background: sc.btn.bg, cursor: 'pointer', fontSize: 13, flexShrink: 0, display: 'flex', alignItems: 'center', justifyContent: 'center' }}>
                    {SI[t.status]}
                  </button>
                  <div style={{ flex: 1, minWidth: 0 }}>
                    <div style={{ display: 'flex', gap: 8, alignItems: 'center', flexWrap: 'wrap' }}>
                      <input value={t.name} onChange={e => update(d => { d.months.find(x => x.id === m.id).tasks.find(x => x.id === t.id).name = e.target.value; return d; })}
                        style={{ fontSize: 14, fontWeight: 500, background: 'none', border: 'none', borderBottom: '1px dashed transparent', flex: 1, minWidth: 90, padding: '1px 2px', textDecoration: t.status === 'done' ? 'line-through' : 'none', color: t.status === 'done' ? '#888' : '#111' }}
                        onFocus={e => e.target.style.borderBottomColor = g.main}
                        onBlur={e => e.target.style.borderBottomColor = 'transparent'} />
                      <input value={t.tag} onChange={e => update(d => { d.months.find(x => x.id === m.id).tasks.find(x => x.id === t.id).tag = e.target.value; return d; })}
                        style={{ fontSize: 11, padding: '2px 9px', borderRadius: 99, border: '1px solid #EDEDE9', background: '#F7F8F6', color: '#555', width: 105 }}
                        onFocus={e => { e.target.style.borderColor = g.main; e.target.style.background = '#E8F7F1'; e.target.style.color = g.dark; }}
                        onBlur={e => { e.target.style.borderColor = '#EDEDE9'; e.target.style.background = '#F7F8F6'; e.target.style.color = '#555'; }} />
                    </div>
                    <input value={t.sub} onChange={e => update(d => { d.months.find(x => x.id === m.id).tasks.find(x => x.id === t.id).sub = e.target.value; return d; })}
                      placeholder="รายละเอียด..."
                      style={{ fontSize: 12, color: '#888', background: 'none', border: 'none', borderBottom: '1px dashed transparent', width: '100%', marginTop: 5, padding: '1px 2px' }}
                      onFocus={e => e.target.style.borderBottomColor = g.main}
                      onBlur={e => e.target.style.borderBottomColor = 'transparent'} />
                  </div>
                  <button className="task-del" onClick={() => update(d => { d.months.find(x => x.id === m.id).tasks = d.months.find(x => x.id === m.id).tasks.filter(x => x.id !== t.id); return d; })}
                    style={{ background: 'none', border: 'none', cursor: 'pointer', color: '#DDD', fontSize: 13, padding: 3, borderRadius: 4, flexShrink: 0 }}>✕</button>
                </div>
              );
            })}
            <button onClick={() => update(d => { d.months.find(x => x.id === m.id).tasks.push({ id: uid(), name: 'งานใหม่', sub: '', tag: '', status: 'pending' }); return d; })}
              style={{ width: '100%', padding: 9, border: '1.5px dashed #EDEDE9', borderRadius: 9, background: 'none', color: '#888', fontSize: 13, cursor: 'pointer', marginTop: 7 }}
              onMouseEnter={e => { e.target.style.borderColor = g.main; e.target.style.color = g.main; e.target.style.background = '#E8F7F1'; }}
              onMouseLeave={e => { e.target.style.borderColor = '#EDEDE9'; e.target.style.color = '#888'; e.target.style.background = 'none'; }}>
              + เพิ่มงาน
            </button>
          </div>
        </div>
      ))}

      <button onClick={() => update(d => { d.months.push({ id: uid(), label: 'เดือนใหม่ 2569', tasks: [] }); return d; })}
        style={{ width: '100%', padding: 13, background: bk, color: 'white', border: 'none', borderRadius: 14, fontSize: 14, fontWeight: 500, cursor: 'pointer', marginBottom: 22 }}
        onMouseEnter={e => e.target.style.background = g.main}
        onMouseLeave={e => e.target.style.background = bk}>
        + เพิ่มเดือนใหม่
      </button>

      {/* Critical */}
      <div style={{ background: 'white', border: '1px solid #FFD0C8', borderRadius: 14, padding: '18px 22px' }}>
        <div style={{ display: 'flex', alignItems: 'center', gap: 10, marginBottom: 12 }}>
          <div style={{ width: 30, height: 30, borderRadius: 7, background: '#FEF0EE', display: 'flex', alignItems: 'center', justifyContent: 'center', fontSize: 16 }}>⚠</div>
          <div style={{ fontSize: 14, fontWeight: 600, color: '#8B1A10' }}>Critical Path — สิ่งที่ต้องระวัง</div>
        </div>
        {data.critical.map((c, i) => (
          <div key={i} className="crit-row" style={{ display: 'flex', alignItems: 'center', gap: 10, padding: '7px 0', borderBottom: i < data.critical.length - 1 ? '1px solid #FEE5E0' : 'none' }}>
            <div style={{ width: 5, height: 5, borderRadius: '50%', background: '#D13B2A', flexShrink: 0 }} />
            <input value={c} onChange={e => update(d => { d.critical[i] = e.target.value; return d; })}
              style={{ flex: 1, background: 'none', border: 'none', borderBottom: '1px dashed transparent', fontSize: 13, color: '#7A1E14', padding: '1px 2px' }}
              onFocus={e => e.target.style.borderBottomColor = '#D13B2A'}
              onBlur={e => e.target.style.borderBottomColor = 'transparent'} />
            <button className="crit-del" onClick={() => update(d => { d.critical.splice(i, 1); return d; })}
              style={{ background: 'none', border: 'none', cursor: 'pointer', color: '#FFAB9A', fontSize: 12, padding: '2px 5px', borderRadius: 4 }}>✕</button>
          </div>
        ))}
        <button onClick={() => update(d => { d.critical.push('รายการใหม่'); return d; })}
          style={{ fontSize: 12, color: '#D13B2A', background: 'none', border: 'none', cursor: 'pointer', padding: '8px 0 0', textDecoration: 'underline', textUnderlineOffset: 2 }}>
          + เพิ่มข้อควรระวัง
        </button>
      </div>
    </div>
  );
}

// ══ VENDORS ═════════════════════════════════════════════════
function Vendors({ data, update, setLb, showToast }) {
  const [filter, setFilter] = useState('');

  const uploadImg = (vid, files) => {
    Array.from(files).forEach(file => {
      const r = new FileReader();
      r.onload = e => {
        update(d => { d.vendors.find(x => x.id === vid).imgs.push(e.target.result); return d; });
        showToast('อัปโหลดรูปแล้ว');
      };
      r.readAsDataURL(file);
    });
  };

  const vendors = data.vendors.filter(v => !filter || v.type === filter);

  return (
    <div>
      <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center', marginBottom: 18, flexWrap: 'wrap', gap: 10 }}>
        <div>
          <div style={{ fontSize: 19, fontWeight: 700 }}>ผู้รับเหมา / ผู้ร่วมงาน</div>
          <div style={{ fontSize: 12, color: '#888', marginTop: 2 }}>ช่างทำร้าน · นักออกแบบ 3D · ดีไซเนอร์</div>
        </div>
        <select value={filter} onChange={e => setFilter(e.target.value)}
          style={{ fontSize: 13, padding: '7px 12px', border: '1px solid #EDEDE9', borderRadius: 8, background: 'white' }}>
          <option value="">ทุกประเภท</option>
          <option value="contractor">ช่างทำร้าน</option>
          <option value="3d">นักออกแบบ 3D</option>
          <option value="design">ดีไซเนอร์/สถาปนิก</option>
          <option value="other">อื่นๆ</option>
        </select>
      </div>

      <div style={{ display: 'grid', gridTemplateColumns: 'repeat(auto-fill,minmax(300px,1fr))', gap: 14 }}>
        {vendors.map(v => {
          const vc = VS_COLOR[v.status] || VS_COLOR.confirm;
          return (
            <div key={v.id} className="vc-card" style={{ background: 'white', border: v.selected ? `2px solid ${g.main}` : '1px solid #EDEDE9', borderRadius: 14, overflow: 'hidden', transition: 'all .2s' }}>
              {/* Top */}
              <div style={{ padding: '14px 16px', borderBottom: '1px solid #EDEDE9' }}>
                <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center', marginBottom: 10 }}>
                  <select value={v.type} onChange={e => update(d => { d.vendors.find(x => x.id === v.id).type = e.target.value; return d; })}
                    style={{ fontSize: 11, padding: '3px 10px', borderRadius: 99, border: '1px solid #EDEDE9', background: '#F7F8F6', color: '#555' }}>
                    <option value="contractor">ช่างทำร้าน</option>
                    <option value="3d">นักออกแบบ 3D</option>
                    <option value="design">ดีไซเนอร์</option>
                    <option value="other">อื่นๆ</option>
                  </select>
                  <div style={{ display: 'flex', alignItems: 'center', gap: 6 }}>
                    {v.selected && <span style={{ fontSize: 10, fontFamily: 'monospace', background: g.main, color: 'white', padding: '2px 8px', borderRadius: 99 }}>เลือกแล้ว</span>}
                    <button className="vendor-del" onClick={() => { if (confirm('ลบผู้รับเหมานี้?')) update(d => { d.vendors = d.vendors.filter(x => x.id !== v.id); return d; }); }}
                      style={{ background: 'none', border: 'none', cursor: 'pointer', color: '#888', fontSize: 13, padding: '3px 7px', borderRadius: 4 }}>✕</button>
                  </div>
                </div>
                <input value={v.name} onChange={e => update(d => { d.vendors.find(x => x.id === v.id).name = e.target.value; return d; })}
                  placeholder="ชื่อบริษัท / ช่าง"
                  style={{ fontSize: 15, fontWeight: 600, background: 'none', border: 'none', borderBottom: '1px dashed transparent', width: '100%', padding: 2 }}
                  onFocus={e => e.target.style.borderBottomColor = g.main}
                  onBlur={e => e.target.style.borderBottomColor = 'transparent'} />
                <input value={v.sub} onChange={e => update(d => { d.vendors.find(x => x.id === v.id).sub = e.target.value; return d; })}
                  placeholder="รายละเอียดงาน..."
                  style={{ fontSize: 12, color: '#888', background: 'none', border: 'none', borderBottom: '1px dashed transparent', width: '100%', padding: 2, marginTop: 4 }}
                  onFocus={e => e.target.style.borderBottomColor = g.main}
                  onBlur={e => e.target.style.borderBottomColor = 'transparent'} />
              </div>

              {/* Meta */}
              <div style={{ padding: '12px 16px', display: 'flex', flexDirection: 'column', gap: 9 }}>
                {[['ติดต่อ', 'contact', 'เบอร์ / LINE / อีเมล'], ['ทำอะไรได้', 'skills', 'scope งาน, ความสามารถ...']].map(([lbl, field, ph]) => (
                  <div key={field} style={{ display: 'flex', alignItems: 'center', gap: 8 }}>
                    <div style={{ fontSize: 11, color: '#888', width: 70, flexShrink: 0 }}>{lbl}</div>
                    <input value={v[field]} onChange={e => update(d => { d.vendors.find(x => x.id === v.id)[field] = e.target.value; return d; })}
                      placeholder={ph}
                      style={{ flex: 1, fontSize: 13, background: 'none', border: 'none', borderBottom: '1px dashed transparent', padding: '1px 2px' }}
                      onFocus={e => e.target.style.borderBottomColor = g.main}
                      onBlur={e => e.target.style.borderBottomColor = 'transparent'} />
                  </div>
                ))}
                <div style={{ display: 'flex', alignItems: 'center', gap: 8 }}>
                  <div style={{ fontSize: 11, color: '#888', width: 70, flexShrink: 0 }}>งบประมาณ</div>
                  <input value={v.budget} onChange={e => update(d => { d.vendors.find(x => x.id === v.id).budget = e.target.value; return d; })}
                    placeholder="0"
                    style={{ fontSize: 14, fontWeight: 600, color: g.main, background: 'none', border: 'none', borderBottom: '1px dashed #EDEDE9', width: 120, padding: '2px 4px', fontFamily: 'Space Mono, monospace' }}
                    onFocus={e => e.target.style.borderBottomColor = g.main}
                    onBlur={e => e.target.style.borderBottomColor = '#EDEDE9'} />
                  <span style={{ fontSize: 12, color: '#888' }}>บาท</span>
                </div>
              </div>

              {/* Status + select */}
              <div style={{ padding: '10px 16px', borderTop: '1px solid #EDEDE9', display: 'flex', alignItems: 'center', justifyContent: 'space-between', gap: 10 }}>
                <select value={v.status} onChange={e => update(d => { d.vendors.find(x => x.id === v.id).status = e.target.value; return d; })}
                  style={{ fontSize: 12, padding: '4px 10px', borderRadius: 99, border: `1px solid ${vc.border}`, background: vc.bg, color: vc.color }}>
                  {Object.entries(VS_LABEL).map(([k, lbl]) => <option key={k} value={k}>{lbl}</option>)}
                </select>
                <label style={{ display: 'flex', alignItems: 'center', gap: 6, fontSize: 13, cursor: 'pointer' }}>
                  <input type="checkbox" checked={v.selected} onChange={e => update(d => { d.vendors.find(x => x.id === v.id).selected = e.target.checked; return d; })} />
                  เลือกคนนี้
                </label>
              </div>

              {/* Photos */}
              <div style={{ padding: '10px 16px', borderTop: '1px solid #EDEDE9' }}>
                <div style={{ fontSize: 10, color: '#888', marginBottom: 7, fontFamily: 'monospace', letterSpacing: '.1em' }}>ผลงาน / รูปที่ส่งมา</div>
                <div style={{ display: 'flex', flexWrap: 'wrap', gap: 7, marginBottom: 8 }}>
                  {(v.imgs || []).map((src, i) => (
                    <img key={i} src={src} alt="" onClick={() => setLb(src)}
                      style={{ width: 66, height: 66, borderRadius: 8, objectFit: 'cover', border: '1px solid #EDEDE9', cursor: 'pointer', transition: 'all .2s' }}
                      onMouseEnter={e => { e.target.style.borderColor = g.main; e.target.style.transform = 'scale(1.05)'; }}
                      onMouseLeave={e => { e.target.style.borderColor = '#EDEDE9'; e.target.style.transform = 'scale(1)'; }}
                      onError={e => e.target.style.display = 'none'} />
                  ))}
                </div>
                <label style={{ border: '1.5px dashed #EDEDE9', borderRadius: 8, padding: '8px 12px', textAlign: 'center', cursor: 'pointer', display: 'flex', alignItems: 'center', justifyContent: 'center', gap: 6, fontSize: 12, color: '#888', transition: 'all .2s' }}
                  onMouseEnter={e => { e.currentTarget.style.borderColor = g.main; e.currentTarget.style.color = g.main; e.currentTarget.style.background = '#E8F7F1'; }}
                  onMouseLeave={e => { e.currentTarget.style.borderColor = '#EDEDE9'; e.currentTarget.style.color = '#888'; e.currentTarget.style.background = 'none'; }}>
                  📎 อัปโหลดรูปภาพ
                  <input type="file" accept="image/*" multiple style={{ display: 'none' }} onChange={e => { uploadImg(v.id, e.target.files); e.target.value = ''; }} />
                </label>
              </div>
            </div>
          );
        })}
      </div>

      <button onClick={() => update(d => { d.vendors.push({ id: uid(), type: 'contractor', name: 'ผู้รับเหมาใหม่', sub: '', contact: '', budget: '', skills: '', status: 'confirm', selected: false, imgs: [] }); return d; })}
        style={{ width: '100%', padding: 13, border: '2px dashed #EDEDE9', borderRadius: 14, background: 'none', color: '#888', fontSize: 14, cursor: 'pointer', marginTop: 4 }}
        onMouseEnter={e => { e.target.style.borderColor = g.main; e.target.style.color = g.main; e.target.style.background = '#E8F7F1'; }}
        onMouseLeave={e => { e.target.style.borderColor = '#EDEDE9'; e.target.style.color = '#888'; e.target.style.background = 'none'; }}>
        + เพิ่มผู้รับเหมา / ผู้ร่วมงาน
      </button>
    </div>
  );
}

// ══ BUDGET ══════════════════════════════════════════════════
function Budget({ data, update }) {
  let grand = 0, paid = 0;
  data.budget.forEach(s => s.rows.forEach(r => { const a = num(r.amt); grand += a; if (r.status === 'paid') paid += a; }));

  return (
    <div>
      <div style={{ background: bk, borderRadius: 14, padding: '18px 24px', display: 'flex', justifyContent: 'space-between', alignItems: 'center', marginBottom: 18 }}>
        <div>
          <div style={{ fontSize: 13, color: '#888' }}>งบประมาณรวมทั้งหมด</div>
          <div style={{ fontSize: 26, fontWeight: 700, fontFamily: 'Space Mono, monospace', color: g.light }}>{fmt(grand)} ฿</div>
          <div style={{ fontSize: 11, color: '#888', marginTop: 3 }}>จ่ายแล้ว {fmt(paid)} ฿</div>
        </div>
        <div style={{ textAlign: 'right' }}>
          <div style={{ fontSize: 11, color: '#888', fontFamily: 'monospace' }}>คงเหลือ</div>
          <div style={{ fontSize: 20, fontWeight: 700, fontFamily: 'Space Mono, monospace', color: g.light }}>{fmt(grand - paid)} ฿</div>
        </div>
      </div>

      {data.budget.map(s => {
        const st = s.rows.reduce((a, r) => a + num(r.amt), 0);
        return (
          <div key={s.id} style={{ background: 'white', border: '1px solid #EDEDE9', borderRadius: 14, padding: '18px 22px', marginBottom: 14 }}>
            <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center', marginBottom: 14 }}>
              <input value={s.title} onChange={e => update(d => { d.budget.find(x => x.id === s.id).title = e.target.value; return d; })}
                style={{ fontSize: 15, fontWeight: 600, background: 'none', border: 'none', borderBottom: '1px dashed transparent', flex: 1, padding: 2 }}
                onFocus={e => e.target.style.borderBottomColor = g.main}
                onBlur={e => e.target.style.borderBottomColor = 'transparent'} />
              <div style={{ display: 'flex', alignItems: 'center', gap: 10 }}>
                <span style={{ fontFamily: 'Space Mono, monospace', fontSize: 15, fontWeight: 700, color: g.main }}>{fmt(st)} ฿</span>
                <button onClick={() => { if (confirm('ลบหมวดงบนี้?')) update(d => { d.budget = d.budget.filter(x => x.id !== s.id); return d; }); }}
                  style={{ background: 'none', border: 'none', cursor: 'pointer', color: '#DDD', fontSize: 13, padding: '2px 5px', borderRadius: 4 }}>✕</button>
              </div>
            </div>
            <table style={{ width: '100%', borderCollapse: 'collapse' }}>
              <thead>
                <tr>{['รายการ', 'จำนวน (฿)', 'สถานะ', ''].map((h, i) => (
                  <th key={i} style={{ fontSize: 11, fontFamily: 'monospace', letterSpacing: '.08em', color: '#888', padding: '7px 8px', borderBottom: '1px solid #EDEDE9', textAlign: i === 1 ? 'right' : 'left' }}>{h}</th>
                ))}</tr>
              </thead>
              <tbody>
                {s.rows.map(r => {
                  const stColor = { paid: { bg: '#E8F7F1', border: '#81C995', color: '#0F5238' }, 'pending-pay': { bg: '#FEF7E0', border: '#FAC775', color: '#C47B00' }, 'not-yet': { bg: '#EDEDE9', border: '#EDEDE9', color: '#555' } }[r.status] || {};
                  return (
                    <tr key={r.id}>
                      <td style={{ padding: '9px 8px', borderBottom: '1px solid #EDEDE9' }}>
                        <input value={r.name} onChange={e => update(d => { d.budget.find(x => x.id === s.id).rows.find(x => x.id === r.id).name = e.target.value; return d; })}
                          placeholder="ชื่อรายการ"
                          style={{ fontSize: 13, background: 'none', border: 'none', borderBottom: '1px dashed transparent', width: '100%', padding: 2 }}
                          onFocus={e => e.target.style.borderBottomColor = g.main}
                          onBlur={e => e.target.style.borderBottomColor = 'transparent'} />
                      </td>
                      <td style={{ padding: '9px 8px', borderBottom: '1px solid #EDEDE9', textAlign: 'right' }}>
                        <input type="number" min="0" value={r.amt} onChange={e => update(d => { d.budget.find(x => x.id === s.id).rows.find(x => x.id === r.id).amt = e.target.value; return d; })}
                          placeholder="0"
                          style={{ fontSize: 13, fontFamily: 'Space Mono, monospace', fontWeight: 600, color: g.main, background: 'none', border: 'none', borderBottom: '1px dashed transparent', width: 110, textAlign: 'right', padding: 2 }}
                          onFocus={e => e.target.style.borderBottomColor = g.main}
                          onBlur={e => e.target.style.borderBottomColor = 'transparent'} />
                      </td>
                      <td style={{ padding: '9px 8px', borderBottom: '1px solid #EDEDE9' }}>
                        <select value={r.status} onChange={e => update(d => { d.budget.find(x => x.id === s.id).rows.find(x => x.id === r.id).status = e.target.value; return d; })}
                          style={{ fontSize: 11, padding: '3px 8px', borderRadius: 99, border: `1px solid ${stColor.border || '#EDEDE9'}`, background: stColor.bg || '#EDEDE9', color: stColor.color || '#555' }}>
                          <option value="not-yet">ยังไม่จ่าย</option>
                          <option value="pending-pay">รอชำระ</option>
                          <option value="paid">จ่ายแล้ว</option>
                        </select>
                      </td>
                      <td style={{ padding: '9px 8px', borderBottom: '1px solid #EDEDE9' }}>
                        <button onClick={() => update(d => { d.budget.find(x => x.id === s.id).rows = d.budget.find(x => x.id === s.id).rows.filter(x => x.id !== r.id); return d; })}
                          style={{ background: 'none', border: 'none', cursor: 'pointer', color: '#DDD', fontSize: 13, padding: '2px 5px', borderRadius: 4 }}>✕</button>
                      </td>
                    </tr>
                  );
                })}
              </tbody>
            </table>
            <button onClick={() => update(d => { d.budget.find(x => x.id === s.id).rows.push({ id: uid(), name: 'รายการใหม่', amt: '', status: 'not-yet' }); return d; })}
              style={{ width: '100%', padding: 9, border: '1.5px dashed #EDEDE9', borderRadius: 9, background: 'none', color: '#888', fontSize: 13, cursor: 'pointer', marginTop: 7 }}
              onMouseEnter={e => { e.target.style.borderColor = g.main; e.target.style.color = g.main; e.target.style.background = '#E8F7F1'; }}
              onMouseLeave={e => { e.target.style.borderColor = '#EDEDE9'; e.target.style.color = '#888'; e.target.style.background = 'none'; }}>
              + เพิ่มรายการ
            </button>
          </div>
        );
      })}

      <button onClick={() => update(d => { d.budget.push({ id: uid(), title: 'หมวดงบใหม่', rows: [{ id: uid(), name: 'รายการ', amt: '', status: 'not-yet' }] }); return d; })}
        style={{ width: '100%', padding: 9, border: '1.5px dashed #EDEDE9', borderRadius: 9, background: 'none', color: '#888', fontSize: 13, cursor: 'pointer', marginTop: 0 }}
        onMouseEnter={e => { e.target.style.borderColor = g.main; e.target.style.color = g.main; e.target.style.background = '#E8F7F1'; }}
        onMouseLeave={e => { e.target.style.borderColor = '#EDEDE9'; e.target.style.color = '#888'; e.target.style.background = 'none'; }}>
        + เพิ่มหมวดงบใหม่
      </button>
    </div>
  );
}
