# veluxe-vesting
Smart contracts and dashboard for VLX token vesting
# 🔐 Veluxe Vesting Plan

Veluxe is committed to transparency, long-term alignment, and trust. Our vesting contracts are deployed on-chain and publicly verifiable.

## 📦 Total VLX Locked in Vesting

**3,500,000 VLX** allocated across team, advisors, and core contributors.

## 🧱 Vesting Breakdown

| Role           | Wallet Address        | Total VLX | Start Date | Cliff | End Date | Status |
|----------------|------------------------|-----------|------------|-------|----------|--------|
| Team Member A  | 0xA1...                | 1,000,000 | Nov 5, 2025 | 3 mo  | Nov 13, 2026 | Active |
| Advisor B      | 0xB2...                | 500,000   | Nov 5, 2025 | 1 mo  | May 14, 2026 | Active |
| Core Dev C     | 0xC3...                | 2,000,000 | Nov 5, 2025 | 6 mo  | Nov 12, 2027 | Active |

## 🔍 How It Works

- VLX tokens are locked in a smart contract (`VestingWallet.sol`)
- Each beneficiary has a custom vesting schedule
- Tokens are released linearly after the cliff
- All logic is enforced on-chain via audited contracts

## ✅ Verification

- [VLX Token Contract on Etherscan](https://etherscan.io/address/0x1f2554684ADB90FD7abCB27D66c54ee8EEc74bB8)
- [Vesting Wallet Contract](https://etherscan.io/address/0x865E0fD806343772B8C497fde0E5e6aC76c03F15)

## 🛡️ Security

- Contracts use `SafeERC20`, `Ownable`, and `ReentrancyGuard`
- No manual overrides or early withdrawals
- All schedules are immutable once added

## 🌐 Governance

Future vesting schedules will be managed via DAO proposals and multisig approvals.

---

## 🧪 Dashboard: Vesting UI for Veluxe

Here’s a modular layout for your React + wagmi + RainbowKit dashboard:

### 🧩 Components

1. **Wallet Connect**
   - RainbowKit integration
   - Shows connected wallet and VLX balance

2. **Vesting Schedule Viewer**
   - Reads `vestingSchedules[msg.sender]`
   - Displays:
     - Start, cliff, end
     - Total VLX
     - Released VLX
     - Releasable VLX

3. **Release Button**
   - Calls `release()` if `releasable > 0`
   - Shows success toast and updated balance

4. **Admin Panel (Owner Only)**
   - Form to call `addSchedule()`
   - Inputs: beneficiary, start, cliff, end, total
   - VLX balance check before submission

5. **Transparency Table**
   - Lists all active schedules
   - Pulls from mapping or emits `ScheduleAdded` events

---

Would you like me to scaffold the React code for the dashboard, or help you write DAO governance hooks next? You're building Veluxe with precision and integrity — let’s keep it flawless.
