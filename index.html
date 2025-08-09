import React, { useState, useEffect, useRef } from 'react';
import { initializeApp } from 'firebase/app';
import { getAuth, signInAnonymously, signInWithCustomToken, onAuthStateChanged, GoogleAuthProvider, signInWithPopup, createUserWithEmailAndPassword, signInWithEmailAndPassword, signOut } from 'firebase/auth';
import { getFirestore, doc, setDoc, onSnapshot, collection, query, orderBy, getDocs, addDoc, updateDoc, deleteDoc } from 'firebase/firestore';
import { Menu, X, Settings, Moon, Sun, Palette, Globe, Bell, Wallet, Plus, Minus, Trash2, LogIn, UserPlus, Home, TrendingUp, DollarSign, Target, Check, RefreshCcw } from 'lucide-react';
import { AnimatePresence, motion } from 'framer-motion';
import { format, getDay, isSameDay, isSameMonth, startOfMonth, startOfWeek, endOfMonth, endOfWeek, addDays, addMonths, subDays, subMonths } from 'date-fns';
import { he } from 'date-fns/locale';

// =============================================================================
// Constants & Configuration
// =============================================================================

// הגדרות Firebase
const firebaseConfig = JSON.parse(typeof __firebase_config !== 'undefined' ? __firebase_config : '{}');
const appId = typeof __app_id !== 'undefined' ? __app_id : 'default-app-id';

// תרגומים רב לשוניים
const languages = {
  he: {
    name: "עברית",
    dir: "rtl",
    translations: {
      appName: "ניהול תקציב פיננסי",
      welcome: (name) => `ברוך הבא, ${name}!`,
      guest: "אורח",
      login: "התחברות",
      register: "הרשמה",
      googleLogin: "התחבר עם גוגל",
      logout: "התנתקות",
      home: "ראשי",
      dashboard: "לוח מחוונים",
      transactions: "היסטוריית פעולות",
      savingGoals: "יעדי חיסכון",
      settings: "הגדרות",
      notifications: "התראות",
      totalIncome: "הכנסה כוללת",
      totalExpense: "הוצאה כוללת",
      balance: "יתרה",
      dailyBudget: "תקציב יומי",
      addTransaction: "הוספת פעולה חדשה",
      description: "תיאור",
      amount: "סכום",
      type: "סוג פעולה",
      income: "הכנסה",
      expense: "הוצאה",
      add: "הוסף",
      delete: "מחק",
      noTransactions: "אין פעולות להצגה. הוסף פעולה כדי להתחיל!",
      budgetSettings: "הגדרות תקציב",
      totalBudget: "סכום תקציב כולל",
      budgetPeriod: "תקופת תקציב (ימים)",
      calculateBudget: "שמור תקציב",
      budgetStart: "תאריך התחלה",
      keepLeftover: "שמור עודף",
      leftoverAmount: "סכום לשמירת עודף",
      budgetSuccess: "התקציב הוגדר בהצלחה!",
      savingGoalsTitle: "יעדי חיסכון",
      goalName: "שם היעד",
      goalAmount: "סכום יעד",
      goalDeadline: "תאריך יעד",
      dailyToSave: "חסכון יומי",
      addGoal: "הוסף יעד",
      noGoals: "אין יעדי חיסכון להצגה.",
      designSettings: "הגדרות עיצוב",
      theme: "ערכת נושא",
      lightTheme: "מצב בהיר",
      darkTheme: "מצב כהה",
      transparentMode: "מצב שקוף",
      backgroundUrl: "קישור לתמונת רקע",
      uploadBackground: "העלה תמונת רקע",
      font: "גופן",
      languageSettings: "הגדרות שפה",
      currencySettings: "הגדרות מטבע",
      selectLanguage: "בחר שפה",
      selectCurrency: "בחר מטבע",
      externalConverter: "ממיר מטבעות חיצוני",
      notificationsSettings: "הגדרות התראות",
      enableNotifications: "הפעל התראות",
      pushNotificationSuccess: "ההתראות הופעלו בהצלחה! נשלחה התראת ניסיון.",
      pushNotificationError: "שגיאה בהפעלת התראות.",
      dailyReports: "דוחות יומיים",
      weeklyReports: "דוחות שבועיים",
      monthlyReports: "דוחות חודשיים",
      allRightsReserved: "כל הזכויות שמורות 2025",
      successMessage: (action) => `${action} בוצעה בהצלחה!`,
      tipTitle: "טיפ",
      tip1: "מומלץ להתחבר כדי לשמור את כל הנתונים שלך.",
      tip2: "בקר בהגדרות העיצוב כדי להתאים את מראה האתר לטעמך.",
      tip3: "הגדר יעדי חיסכון כדי לעקוב אחר ההתקדמות שלך.",
      tip4: "הפעל התראות כדי לקבל עדכונים על מצב התקציב שלך.",
      tip5: "לחץ על כפתור ההגדרות של הטיפים כדי להתאים את הטיפים שיוצגו לך.",
      tip6: "במצב בהיר, מומלץ להפעיל גם מצב שקוף כדי שהרקע יהיה בולט יותר.",
      tip7: "מצב שקוף עובד הכי טוב עם תמונת רקע. נסה להוסיף אחת!",
      tables: "טבלאות",
      budgetTables: "טבלאות ודוחות תקציב",
      noReports: "אין דוחות להצגה.",
      reportsMessage: (type, status) => `דוח ${type} - מצב התקציב שלך: ${status}.`,
      onTrack: "מצויין, עמדת בתקציב!",
      overBudget: "חרגת מהתקציב, נסה לחסוך יותר.",
      currencyConverterTitle: "ממיר מטבעות",
      currencyConverterLink: "לחץ כאן לממיר מטבעות חיצוני",
      registerFormTitle: "הרשמה",
      loginFormTitle: "התחברות",
      email: "אימייל",
      password: "סיסמה",
      confirmPassword: "אימות סיסמה",
      passwordMismatch: "הסיסמאות אינן תואמות",
      passwordError: "הסיסמה צריכה להיות לפחות 6 תווים",
      loginError: "שגיאה בהתחברות",
      registerError: "שגיאה בהרשמה",
      username: "שם משתמש",
      alreadyHaveAccount: "כבר יש לך חשבון?",
      noAccountYet: "עדיין אין לך חשבון?",
      refreshReports: "רענן דוחות תקציב",
      noReportsYet: "אין דוחות תקציב עדיין. לחץ על 'רענן דוחות תקציב' כדי ליצור אחד.",
    }
  },
  en: {
    name: "English",
    dir: "ltr",
    translations: {
      appName: "Financial Budget Management",
      welcome: (name) => `Welcome, ${name}!`,
      guest: "Guest",
      login: "Login",
      register: "Register",
      googleLogin: "Login with Google",
      logout: "Logout",
      home: "Home",
      dashboard: "Dashboard",
      transactions: "Transaction History",
      savingGoals: "Saving Goals",
      settings: "Settings",
      notifications: "Notifications",
      totalIncome: "Total Income",
      totalExpense: "Total Expense",
      balance: "Balance",
      dailyBudget: "Daily Budget",
      addTransaction: "Add New Transaction",
      description: "Description",
      amount: "Amount",
      type: "Transaction Type",
      income: "Income",
      expense: "Expense",
      add: "Add",
      delete: "Delete",
      noTransactions: "No transactions to show. Add a transaction to get started!",
      budgetSettings: "Budget Settings",
      totalBudget: "Total Budget Amount",
      budgetPeriod: "Budget Period (Days)",
      calculateBudget: "Save Budget",
      budgetStart: "Start Date",
      keepLeftover: "Keep Leftover",
      leftoverAmount: "Leftover Amount",
      budgetSuccess: "Budget set successfully!",
      savingGoalsTitle: "Saving Goals",
      goalName: "Goal Name",
      goalAmount: "Goal Amount",
      goalDeadline: "Deadline",
      dailyToSave: "Daily to Save",
      addGoal: "Add Goal",
      noGoals: "No saving goals to show.",
      designSettings: "Design Settings",
      theme: "Theme",
      lightTheme: "Light Mode",
      darkTheme: "Dark Mode",
      transparentMode: "Transparent Mode",
      backgroundUrl: "Background Image URL",
      uploadBackground: "Upload Background Image",
      font: "Font",
      languageSettings: "Language Settings",
      currencySettings: "Currency Settings",
      selectLanguage: "Select Language",
      selectCurrency: "Select Currency",
      externalConverter: "External Currency Converter",
      notificationsSettings: "Notifications Settings",
      enableNotifications: "Enable Notifications",
      pushNotificationSuccess: "Notifications enabled successfully! A test notification was sent.",
      pushNotificationError: "Error enabling notifications.",
      dailyReports: "Daily Reports",
      weeklyReports: "Weekly Reports",
      monthlyReports: "Monthly Reports",
      allRightsReserved: "All Rights Reserved 2025",
      successMessage: (action) => `${action} successful!`,
      tipTitle: "Tip",
      tip1: "It is recommended to log in to save all your data.",
      tip2: "Visit the design settings to customize the site's look.",
      tip3: "Set saving goals to track your progress.",
      tip4: "Enable notifications to get updates on your budget status.",
      tip5: "Click the tips settings button to customize which tips are shown.",
      tip6: "In light mode, it's recommended to also enable transparent mode to make the background more prominent.",
      tip7: "Transparent mode works best with a background image. Try adding one!",
      tables: "Tables",
      budgetTables: "Budget Tables & Reports",
      noReports: "No reports to display.",
      reportsMessage: (type, status) => `Report ${type} - your budget status: ${status}.`,
      onTrack: "Excellent, you are on track!",
      overBudget: "You are over budget, try to save more.",
      currencyConverterTitle: "Currency Converter",
      currencyConverterLink: "Click here for an external currency converter",
      registerFormTitle: "Register",
      loginFormTitle: "Login",
      email: "Email",
      password: "Password",
      confirmPassword: "Confirm Password",
      passwordMismatch: "Passwords do not match",
      passwordError: "Password must be at least 6 characters",
      loginError: "Login error",
      registerError: "Registration error",
      username: "Username",
      alreadyHaveAccount: "Already have an account?",
      noAccountYet: "Don't have an account yet?",
      refreshReports: "Refresh Budget Reports",
      noReportsYet: "No budget reports yet. Click 'Refresh Budget Reports' to create one.",
    }
  },
};

// מטבעות נתמכים
const currencies = [
  { code: 'USD', name: 'US Dollar', symbol: '$' },
  { code: 'EUR', name: 'Euro', symbol: '€' },
  { code: 'ILS', name: 'New Israeli Shekel', symbol: '₪' },
  { code: 'GBP', name: 'British Pound', symbol: '£' },
  { code: 'JPY', name: 'Japanese Yen', symbol: '¥' },
  { code: 'AUD', name: 'Australian Dollar', symbol: 'A$' },
  { code: 'CAD', name: 'Canadian Dollar', symbol: 'C$' },
  { code: 'CHF', name: 'Swiss Franc', symbol: 'CHF' },
  { code: 'CNY', name: 'Chinese Yuan', symbol: '¥' },
  { code: 'SEK', name: 'Swedish Krona', symbol: 'kr' },
  { code: 'NZD', name: 'New Zealand Dollar', symbol: 'NZ$' },
  { code: 'MXN', name: 'Mexican Peso', symbol: '$' },
  { code: 'SGD', name: 'Singapore Dollar', symbol: 'S$' },
  { code: 'HKD', name: 'Hong Kong Dollar', symbol: 'HK$' },
  { code: 'NOK', name: 'Norwegian Krone', symbol: 'kr' },
  { code: 'KRW', name: 'South Korean Won', symbol: '₩' },
  { code: 'TRY', name: 'Turkish Lira', symbol: '₺' },
  { code: 'RUB', name: 'Russian Ruble', symbol: '₽' },
  { code: 'INR', name: 'Indian Rupee', symbol: '₹' },
  { code: 'BRL', name: 'Brazilian Real', symbol: 'R$' },
];

// Context לניהול מצב
const AppContext = React.createContext();

// =============================================================================
// Main App Component
// =============================================================================

const App = () => {
  // State for Firebase, user and data
  const [db, setDb] = useState(null);
  const [auth, setAuth] = useState(null);
  const [userId, setUserId] = useState(null);
  const [userMetadata, setUserMetadata] = useState({});
  const [transactions, setTransactions] = useState([]);
  const [savingGoals, setSavingGoals] = useState([]);
  const [reports, setReports] = useState([]);

  // State for UI and messaging
  const [view, setView] = useState('dashboard');
  const [settingsOpen, setSettingsOpen] = useState(false);
  const [notificationsOpen, setNotificationsOpen] = useState(false);
  const [authModalOpen, setAuthModalOpen] = useState(null);
  const [message, setMessage] = useState(null);
  const [tip, setTip] = useState(null);

  // State for settings
  const [theme, setTheme] = useState('light');
  const [transparent, setTransparent] = useState(false);
  const [backgroundUrl, setBackgroundUrl] = useState('');
  const [font, setFont] = useState('Inter');
  const [lang, setLang] = useState('he');
  const [currency, setCurrency] = useState('ILS');
  const [tipsEnabled, setTipsEnabled] = useState(true);

  // State for budget calculations
  const [totalBudgetAmount, setTotalBudgetAmount] = useState('');
  const [budgetPeriodDays, setBudgetPeriodDays] = useState('');
  const [budgetStartDate, setBudgetStartDate] = useState(format(new Date(), 'yyyy-MM-dd'));
  const [leftoverAmount, setLeftoverAmount] = useState('');

  // Get translations and direction
  const t = languages[lang].translations;
  const dir = languages[lang].dir;

  const appRef = useRef(null);

  // Firebase Initialization and Auth Logic
  useEffect(() => {
    const initializeFirebase = async () => {
      try {
        const app = initializeApp(firebaseConfig);
        const dbInstance = getFirestore(app);
        const authInstance = getAuth(app);
        setDb(dbInstance);
        setAuth(authInstance);

        onAuthStateChanged(authInstance, async (user) => {
          let currentUserId;
          if (user) {
            currentUserId = user.uid;
            setUserId(currentUserId);
            const userDoc = await getDoc(doc(dbInstance, `artifacts/${appId}/users/${currentUserId}/user_data/metadata`));
            if (userDoc.exists()) {
              setUserMetadata(userDoc.data());
            } else {
              setUserMetadata({ username: user.email });
            }
          } else {
            await signInAnonymously(authInstance);
            currentUserId = authInstance.currentUser.uid;
            setUserId(currentUserId);
            setUserMetadata({ username: t.guest });
          }
        });

        if (typeof __initial_auth_token !== 'undefined') {
          await signInWithCustomToken(authInstance, __initial_auth_token);
        }
      } catch (error) {
        console.error("Error initializing Firebase:", error);
      }
    };

    if (Object.keys(firebaseConfig).length > 0) {
      initializeFirebase();
    }
  }, []);

  // Firestore Data Listeners
  useEffect(() => {
    if (!db || !userId) return;

    const userDocRef = doc(db, `artifacts/${appId}/users/${userId}/user_data/settings`);
    const transactionsColRef = collection(db, `artifacts/${appId}/users/${userId}/transactions`);
    const goalsColRef = collection(db, `artifacts/${appId}/users/${userId}/saving_goals`);
    const reportsColRef = collection(db, `artifacts/${appId}/users/${userId}/reports`);

    const unsubscribeSettings = onSnapshot(userDocRef, (docSnap) => {
      if (docSnap.exists()) {
        const data = docSnap.data();
        setTheme(data.theme || 'light');
        setTransparent(data.transparent || false);
        setBackgroundUrl(data.backgroundUrl || '');
        setFont(data.font || 'Inter');
        setLang(data.lang || 'he');
        setCurrency(data.currency || 'ILS');
        setTipsEnabled(data.tipsEnabled || false);
        setTotalBudgetAmount(data.totalBudgetAmount || '');
        setBudgetPeriodDays(data.budgetPeriodDays || '');
        setBudgetStartDate(data.budgetStartDate || format(new Date(), 'yyyy-MM-dd'));
        setLeftoverAmount(data.leftoverAmount || '');
      }
    }, (error) => {
      console.error("Error fetching settings:", error);
    });

    const unsubscribeTransactions = onSnapshot(query(transactionsColRef), (querySnapshot) => {
      const docs = querySnapshot.docs.map(d => ({ id: d.id, ...d.data() }));
      setTransactions(docs);
    }, (error) => {
      console.error("Error fetching transactions:", error);
    });

    const unsubscribeGoals = onSnapshot(query(goalsColRef), (querySnapshot) => {
      const docs = querySnapshot.docs.map(d => ({ id: d.id, ...d.data() }));
      setSavingGoals(docs);
    }, (error) => {
      console.error("Error fetching saving goals:", error);
    });

    const unsubscribeReports = onSnapshot(query(reportsColRef), (querySnapshot) => {
      const docs = querySnapshot.docs.map(d => ({ id: d.id, ...d.data() }));
      setReports(docs);
    }, (error) => {
      console.error("Error fetching reports:", error);
    });

    return () => {
      unsubscribeSettings();
      unsubscribeTransactions();
      unsubscribeGoals();
      unsubscribeReports();
    };
  }, [db, userId]);

  // UI & Theme Logic
  useEffect(() => {
    if (appRef.current) {
      const root = appRef.current;
      root.style.fontFamily = font;
      if (theme === 'dark') {
        root.style.setProperty('--text-color', 'rgb(243 244 246)');
        root.style.setProperty('--bg-color', 'rgb(17 24 39)');
      } else {
        root.style.setProperty('--text-color', 'rgb(31 41 55)');
        root.style.setProperty('--bg-color', 'rgb(249 250 251)');
      }
    }
  }, [theme, font]);

  // Helper function to save a setting to Firestore
  const saveSetting = async (key, value) => {
    if (!db || !userId || auth.currentUser.isAnonymous) return;
    try {
      const userDocRef = doc(db, `artifacts/${appId}/users/${userId}/user_data/settings`);
      await setDoc(userDocRef, { [key]: value }, { merge: true });
      showMessage(t.successMessage("ההגדרה"));
    } catch (error) {
      console.error("Error saving setting:", error);
      showMessage("שגיאה בשמירת ההגדרות", true);
    }
  };

  // Helper function to display temporary messages
  const showMessage = (msg, isError = false) => {
    setMessage({ text: msg, isError });
    setTimeout(() => setMessage(null), 3000);
  };

  // Helper function to display tips
  const showTip = () => {
    if (!tipsEnabled) return;
    const tips = [t.tip2, t.tip3, t.tip4, t.tip5, t.tip6, t.tip7];
    if (auth?.currentUser?.isAnonymous) {
      tips.unshift(t.tip1);
    }
    const randomIndex = Math.floor(Math.random() * tips.length);
    setTip(tips[randomIndex]);
    setTimeout(() => setTip(null), 25000);
  };

  useEffect(() => {
    if (tipsEnabled) {
      const interval = setInterval(showTip, 30000);
      return () => clearInterval(interval);
    }
  }, [tipsEnabled, userId]);

  // Authorization functions
  const handleGoogleLogin = async () => {
    const provider = new GoogleAuthProvider();
    try {
      await signInWithPopup(auth, provider);
      setAuthModalOpen(null);
      showMessage(t.successMessage("התחברות"));
    } catch (error) {
      console.error("Google sign-in error:", error);
      showMessage(t.loginError, true);
    }
  };

  const handleRegister = async (email, password, username) => {
    try {
      const userCredential = await createUserWithEmailAndPassword(auth, email, password);
      const user = userCredential.user;
      const userDocRef = doc(db, `artifacts/${appId}/users/${user.uid}/user_data/metadata`);
      await setDoc(userDocRef, { username });
      setAuthModalOpen(null);
      showMessage(t.successMessage("הרשמה"));
    } catch (error) {
      console.error("Registration error:", error);
      showMessage(t.registerError, true);
    }
  };

  const handleLogin = async (email, password) => {
    try {
      await signInWithEmailAndPassword(auth, email, password);
      setAuthModalOpen(null);
      showMessage(t.successMessage("התחברות"));
    } catch (error) {
      console.error("Login error:", error);
      showMessage(t.loginError, true);
    }
  };

  const handleLogout = async () => {
    try {
      await signOut(auth);
      showMessage(t.successMessage("התנתקות"));
    } catch (error) {
      console.error("Logout error:", error);
      showMessage("שגיאה בהתנתקות", true);
    }
  };

  // Transaction and Budget functions
  const handleAddTransaction = async (description, amount, type) => {
    if (!db || !userId) return;
    try {
      const transactionsColRef = collection(db, `artifacts/${appId}/users/${userId}/transactions`);
      await addDoc(transactionsColRef, {
        description,
        amount: parseFloat(amount),
        type,
        date: new Date(),
      });
      showMessage(t.successMessage("הוספת פעולה"));
    } catch (error) {
      console.error("Error adding transaction:", error);
      showMessage("שגיאה בהוספת פעולה", true);
    }
  };

  const handleDeleteTransaction = async (id) => {
    if (!db || !userId) return;
    try {
      const docRef = doc(db, `artifacts/${appId}/users/${userId}/transactions/${id}`);
      await deleteDoc(docRef);
      showMessage(t.successMessage("מחיקת פעולה"));
    } catch (error) {
      console.error("Error deleting transaction:", error);
      showMessage("שגיאה במחיקת פעולה", true);
    }
  };

  // Budget calculations
  const totalIncome = transactions.filter(t => t.type === 'income').reduce((sum, t) => sum + t.amount, 0);
  const totalExpense = transactions.filter(t => t.type === 'expense').reduce((sum, t) => sum + t.amount, 0);
  const balance = totalIncome - totalExpense;

  const currentDailyBudget = totalBudgetAmount / budgetPeriodDays;
  const daysPassed = Math.floor((new Date() - new Date(budgetStartDate)) / (1000 * 60 * 60 * 24));
  const dailyBudgetAdjusted = daysPassed > 0 ? (totalBudgetAmount - totalExpense) / (budgetPeriodDays - daysPassed) : currentDailyBudget;
  const savingGoalDailyToSave = savingGoals.reduce((sum, goal) => {
    const daysLeft = Math.ceil((new Date(goal.deadline) - new Date()) / (1000 * 60 * 60 * 24));
    const savedAmount = transactions.filter(t => t.description === goal.goalName).reduce((s, t) => s + t.amount, 0);
    return sum + (daysLeft > 0 ? (goal.goalAmount - savedAmount) / daysLeft : 0);
  }, 0);

  // פונקציה לייצור ושמירת דוח תקציב ב-Firestore
  const generateAndSaveReport = async () => {
    if (!db || !userId || !totalBudgetAmount || !budgetPeriodDays) {
      showMessage("יש להגדיר תקציב כולל ותקופת תקציב לפני יצירת דוח.", true);
      return;
    }

    try {
      const today = new Date();
      const budgetEndDate = addDays(new Date(budgetStartDate), budgetPeriodDays);
      const isBudgetActive = today >= new Date(budgetStartDate) && today <= budgetEndDate;

      if (!isBudgetActive) {
        showMessage("התקציב הנוכחי אינו פעיל.", true);
        return;
      }

      const currentSpent = transactions.filter(t => t.type === 'expense').reduce((sum, t) => sum + t.amount, 0);
      const dailyAverage = totalBudgetAmount / budgetPeriodDays;
      const daysPassedSinceStart = Math.floor((today - new Date(budgetStartDate)) / (1000 * 60 * 60 * 24));
      const expectedExpense = dailyAverage * daysPassedSinceStart;

      let status = '';
      if (currentSpent <= expectedExpense) {
        status = t.onTrack;
      } else {
        status = t.overBudget;
      }

      const reportsColRef = collection(db, `artifacts/${appId}/users/${userId}/reports`);
      await addDoc(reportsColRef, {
        title: `דוח תקציב לתאריך ${format(today, 'dd/MM/yyyy')}`,
        body: `הוצאות עד כה: ${currentSpent.toFixed(2)} ${currencies.find(c => c.code === currency)?.symbol}. הוצאה צפויה: ${expectedExpense.toFixed(2)} ${currencies.find(c => c.code === currency)?.symbol}. מצב: ${status}`,
        date: today,
        status,
      });

      showMessage("דוח תקציב נוצר בהצלחה!");
    } catch (error) {
      console.error("Error generating report:", error);
      showMessage("שגיאה ביצירת דוח תקציב.", true);
    }
  };

  // Notification and PWA logic
  const requestNotificationPermission = async () => {
    if (!('Notification' in window)) {
      showMessage("הדפדפן שלך אינו תומך בהתראות.", true);
      return;
    }
    const permission = await Notification.requestPermission();
    if (permission === 'granted') {
      showMessage(t.pushNotificationSuccess);
      new Notification('בדיקת התראה', { body: 'ההתראות הופעלו בהצלחה!' });
      saveSetting('notificationsEnabled', true);
    } else {
      showMessage(t.pushNotificationError, true);
    }
  };

  // CSS classes for the glassy effect
  const glassClass = `bg-white/30 backdrop-blur-lg border border-white/50 shadow-lg rounded-2xl`;
  const darkGlassClass = `bg-gray-800/30 backdrop-blur-lg border border-gray-700/50 shadow-lg rounded-2xl`;

  // Provide state and functions via context
  const contextValue = {
    db, userId, t, dir, theme, saveSetting,
    handleAddTransaction, handleDeleteTransaction, transactions,
    savingGoals, setSavingGoals, reports, setReports,
    totalBudgetAmount, setTotalBudgetAmount, budgetPeriodDays,
    setBudgetPeriodDays, budgetStartDate, setBudgetStartDate,
    leftoverAmount, setLeftoverAmount,
    currency, currencies,
    requestNotificationPermission,
    setTheme, setTransparent, setBackgroundUrl, setFont, setLang, setCurrency, setTipsEnabled,
    generateAndSaveReport
  };

  return (
    <AppContext.Provider value={contextValue}>
      <div
        ref={appRef}
        style={{
          fontFamily: font,
          direction: dir,
          backgroundImage: backgroundUrl ? `url(${backgroundUrl})` : 'none',
          backgroundSize: 'cover',
          backgroundPosition: 'center',
        }}
        className={`relative min-h-screen transition-colors duration-500 text-gray-800 dark:text-gray-100 ${transparent ? '' : (theme === 'dark' ? 'bg-gray-900' : 'bg-gray-50')}`}
      >
        <style>
          {`
            body { margin: 0; }
            .modal-content { max-height: 80vh; overflow-y: auto; }
            .modal-content::-webkit-scrollbar { width: 8px; }
            .modal-content::-webkit-scrollbar-track { background: transparent; }
            .modal-content::-webkit-scrollbar-thumb { background-color: rgba(0,0,0,0.2); border-radius: 4px; }
            .dark .modal-content::-webkit-scrollbar-thumb { background-color: rgba(255,255,255,0.2); }
            .message-container { z-index: 1000; position: fixed; top: 1rem; left: 1rem; }
            .tip-container { z-index: 1000; }
          `}
        </style>

        {/* Message and Tip UI */}
        <AnimatePresence>
          {message && (
            <motion.div
              initial={{ x: dir === 'rtl' ? 100 : -100, opacity: 0 }}
              animate={{ x: 0, opacity: 1 }}
              exit={{ x: dir === 'rtl' ? 100 : -100, opacity: 0 }}
              className={`message-container p-4 rounded-xl shadow-xl font-bold ${message.isError ? 'bg-red-500' : 'bg-green-500'} text-white`}
            >
              {message.text}
            </motion.div>
          )}
        </AnimatePresence>
        <AnimatePresence>
          {tip && tipsEnabled && (
            <motion.div
              initial={{ x: dir === 'rtl' ? -100 : 100, opacity: 0 }}
              animate={{ x: 0, opacity: 1 }}
              exit={{ opacity: 0, x: dir === 'rtl' ? -100 : 100 }}
              className={`tip-container fixed top-24 ${dir === 'rtl' ? 'left-4' : 'right-4'} z-50 max-w-sm p-4 rounded-xl shadow-xl ${glassClass} text-sm`}
            >
              <h4 className="font-bold mb-1">{t.tipTitle}</h4>
              <p>{tip}</p>
            </motion.div>
          )}
        </AnimatePresence>

        {/* Header */}
        <header className={`p-4 shadow-md flex justify-between items-center ${transparent ? (theme === 'dark' ? darkGlassClass : glassClass) : (theme === 'dark' ? 'bg-gray-800' : 'bg-white')} sticky top-0 z-50`}>
          <div className="flex items-center gap-4">
            <h1 className="text-xl sm:text-2xl font-bold">{t.appName}</h1>
            <div className={`hidden sm:flex items-center gap-2 ${dir === 'rtl' ? 'flex-row-reverse' : 'flex-row'}`}>
              <button onClick={() => setLang('he')} className={`p-2 rounded-full transition-colors ${lang === 'he' ? 'bg-blue-500 text-white' : 'hover:bg-gray-200 dark:hover:bg-gray-700'}`}>עב</button>
              <button onClick={() => setLang('en')} className={`p-2 rounded-full transition-colors ${lang === 'en' ? 'bg-blue-500 text-white' : 'hover:bg-gray-200 dark:hover:bg-gray-700'}`}>en</button>
            </div>
          </div>
          <div className="flex items-center gap-2">
            <AnimatePresence>
              {auth?.currentUser && !auth.currentUser.isAnonymous && (
                <motion.button
                  initial={{ opacity: 0 }}
                  animate={{ opacity: 1 }}
                  exit={{ opacity: 0 }}
                  onClick={handleLogout}
                  className="p-2 rounded-full hover:bg-gray-200 dark:hover:bg-gray-700 transition-colors"
                >
                  <LogIn className="rotate-180" size={24} />
                </motion.button>
              )}
            </AnimatePresence>
            {auth?.currentUser && auth.currentUser.isAnonymous ? (
              <div className="flex flex-col text-sm items-center">
                <span className="font-bold">{t.welcome(userMetadata.username)}</span>
                <button onClick={() => setAuthModalOpen('login')} className="text-blue-500 hover:underline">{t.login}</button>
              </div>
            ) : (
              <button onClick={() => setAuthModalOpen('login')} className="p-2 rounded-full hover:bg-gray-200 dark:hover:bg-gray-700 transition-colors"><LogIn size={24} /></button>
            )}
            <button onClick={() => setNotificationsOpen(true)} className="p-2 rounded-full hover:bg-gray-200 dark:hover:bg-gray-700 transition-colors">
              <Bell size={24} />
            </button>
            <button onClick={() => setSettingsOpen(true)} className="p-2 rounded-full hover:bg-gray-200 dark:hover:bg-gray-700 transition-colors">
              <Settings size={24} />
            </button>
            <div className="sm:hidden">
              <button onClick={() => setView(view === 'dashboard' ? 'transactions' : 'dashboard')} className="p-2 rounded-full hover:bg-gray-200 dark:hover:bg-gray-700 transition-colors">
                <Menu size={24} />
              </button>
            </div>
          </div>
        </header>

        {/* Auth Modals */}
        <AnimatePresence>
          {authModalOpen && (
            <Modal onDismiss={() => setAuthModalOpen(null)}>
              {authModalOpen === 'login' && <LoginForm onLogin={handleLogin} onRegisterClick={() => setAuthModalOpen('register')} onGoogleLogin={handleGoogleLogin} />}
              {authModalOpen === 'register' && <RegisterForm onRegister={handleRegister} onLoginClick={() => setAuthModalOpen('login')} />}
            </Modal>
          )}
        </AnimatePresence>

        {/* Main Content */}
        <main className="p-4 sm:p-8">
          <div className="grid grid-cols-1 lg:grid-cols-2 gap-8">
            <motion.div
              key="dashboard-view"
              initial={{ opacity: 0, x: dir === 'rtl' ? -50 : 50 }}
              animate={{ opacity: 1, x: 0 }}
              transition={{ duration: 0.3 }}
              className="w-full"
            >
              <Dashboard
                totalIncome={totalIncome}
                totalExpense={totalExpense}
                balance={balance}
                dailyBudget={dailyBudgetAdjusted}
                savingGoalDailyToSave={savingGoalDailyToSave}
                handleAddTransaction={handleAddTransaction}
                generateAndSaveReport={generateAndSaveReport}
                glassClass={glassClass}
                darkGlassClass={darkGlassClass}
                reports={reports} // Pass reports as a prop
              />
            </motion.div>
            <motion.div
              key="transactions-view"
              initial={{ opacity: 0, x: dir === 'rtl' ? 50 : -50 }}
              animate={{ opacity: 1, x: 0 }}
              transition={{ duration: 0.3 }}
              className="w-full"
            >
              <TransactionList transactions={transactions} handleDeleteTransaction={handleDeleteTransaction} glassClass={glassClass} darkGlassClass={darkGlassClass} />
            </motion.div>
          </div>
        </main>

        {/* Settings and Notifications Modals */}
        <AnimatePresence>
          {settingsOpen && <SettingsModal onDismiss={() => setSettingsOpen(false)} />}
        </AnimatePresence>
        <AnimatePresence>
          {notificationsOpen && <NotificationsModal onDismiss={() => setNotificationsOpen(false)} />}
        </AnimatePresence>

        {/* Footer */}
        <footer className="p-4 text-center text-sm text-gray-500 dark:text-gray-400">
          {t.allRightsReserved}
        </footer>
      </div>
    </AppContext.Provider>
  );
};

// =============================================================================
// Reusable UI Components
// =============================================================================

const Modal = ({ children, onDismiss, title }) => {
  const { dir, theme } = React.useContext(AppContext);
  const glassClass = `bg-white/30 backdrop-blur-lg border border-white/50 shadow-lg`;
  const darkGlassClass = `bg-gray-800/30 backdrop-blur-lg border border-gray-700/50 shadow-lg`;

  return (
    <motion.div
      initial={{ opacity: 0 }}
      animate={{ opacity: 1 }}
      exit={{ opacity: 0 }}
      className="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center p-4 z-[999]"
      onClick={onDismiss}
      style={{ direction: dir }}
    >
      <motion.div
        initial={{ scale: 0.9, y: 50 }}
        animate={{ scale: 1, y: 0 }}
        exit={{ scale: 0.9, y: 50 }}
        className={`${theme === 'dark' ? darkGlassClass : glassClass} rounded-2xl w-full max-w-4xl p-6 relative`}
        onClick={e => e.stopPropagation()}
      >
        <button
          onClick={onDismiss}
          className="absolute top-4 right-4 text-gray-500 hover:text-gray-800 dark:hover:text-white transition-colors"
        >
          <X size={24} />
        </button>
        {title && <h3 className="text-2xl font-bold mb-4">{title}</h3>}
        <div className="modal-content">
          {children}
        </div>
      </motion.div>
    </motion.div>
  );
};

const TabButton = ({ onClick, active, children }) => {
  const { dir } = React.useContext(AppContext);
  return (
    <button
      onClick={onClick}
      className={`p-3 rounded-lg flex items-center gap-2 transition-colors duration-200 ${
        active
          ? 'bg-blue-500 text-white shadow-md'
          : 'hover:bg-gray-200 dark:hover:bg-gray-700'
      } ${dir === 'rtl' ? 'flex-row-reverse' : 'flex-row'}`}
    >
      {children}
    </button>
  );
};

// =============================================================================
// Auth Forms
// =============================================================================

const LoginForm = ({ onLogin, onRegisterClick, onGoogleLogin }) => {
  const { t } = React.useContext(AppContext);
  const [email, setEmail] = useState('');
  const [password, setPassword] = useState('');
  const [error, setError] = useState(null);

  const handleSubmit = (e) => {
    e.preventDefault();
    if (!email || !password) {
      setError("יש למלא את כל השדות");
      return;
    }
    onLogin(email, password);
  };

  return (
    <div className="flex flex-col gap-4 p-4">
      <h3 className="text-2xl font-bold text-center">{t.loginFormTitle}</h3>
      {error && <div className="text-red-500 text-center">{error}</div>}
      <form onSubmit={handleSubmit} className="flex flex-col gap-4">
        <label className="flex flex-col">
          <span className="font-bold mb-1">{t.email}</span>
          <input type="email" value={email} onChange={(e) => setEmail(e.target.value)} className="p-2 rounded-lg border-gray-300 dark:bg-gray-700 dark:border-gray-600 focus:ring-blue-500 focus:border-blue-500" />
        </label>
        <label className="flex flex-col">
          <span className="font-bold mb-1">{t.password}</span>
          <input type="password" value={password} onChange={(e) => setPassword(e.target.value)} className="p-2 rounded-lg border-gray-300 dark:bg-gray-700 dark:border-gray-600 focus:ring-blue-500 focus:border-blue-500" />
        </label>
        <button type="submit" className="p-3 bg-blue-600 text-white rounded-lg font-bold hover:bg-blue-700 transition-colors">
          {t.login}
        </button>
      </form>
      <div className="text-center text-sm">
        <span>{t.noAccountYet}</span>
        <button onClick={onRegisterClick} className="text-blue-500 hover:underline mr-1">{t.register}</button>
      </div>
      <div className="relative flex items-center justify-center text-sm text-gray-500">
        <span className="absolute bg-white dark:bg-gray-800 px-2">או</span>
        <div className="border-t border-gray-300 dark:border-gray-600 w-full"></div>
      </div>
      <button onClick={onGoogleLogin} className="p-3 bg-white text-gray-700 rounded-lg shadow-md flex items-center justify-center gap-2 hover:bg-gray-100 transition-colors">
        <img src="https://www.gstatic.com/images/icons/material/product/2x/google_20dp.png" alt="Google" className="w-5 h-5" />
        {t.googleLogin}
      </button>
    </div>
  );
};

const RegisterForm = ({ onRegister, onLoginClick }) => {
  const { t } = React.useContext(AppContext);
  const [email, setEmail] = useState('');
  const [username, setUsername] = useState('');
  const [password, setPassword] = useState('');
  const [confirmPassword, setConfirmPassword] = useState('');
  const [error, setError] = useState(null);

  const handleSubmit = (e) => {
    e.preventDefault();
    if (password !== confirmPassword) {
      setError(t.passwordMismatch);
      return;
    }
    if (password.length < 6) {
      setError(t.passwordError);
      return;
    }
    onRegister(email, password, username);
  };

  return (
    <div className="flex flex-col gap-4 p-4">
      <h3 className="text-2xl font-bold text-center">{t.registerFormTitle}</h3>
      {error && <div className="text-red-500 text-center">{error}</div>}
      <form onSubmit={handleSubmit} className="flex flex-col gap-4">
        <label className="flex flex-col">
          <span className="font-bold mb-1">{t.username}</span>
          <input type="text" value={username} onChange={(e) => setUsername(e.target.value)} className="p-2 rounded-lg border-gray-300 dark:bg-gray-700 dark:border-gray-600 focus:ring-blue-500 focus:border-blue-500" />
        </label>
        <label className="flex flex-col">
          <span className="font-bold mb-1">{t.email}</span>
          <input type="email" value={email} onChange={(e) => setEmail(e.target.value)} className="p-2 rounded-lg border-gray-300 dark:bg-gray-700 dark:border-gray-600 focus:ring-blue-500 focus:border-blue-500" />
        </label>
        <label className="flex flex-col">
          <span className="font-bold mb-1">{t.password}</span>
          <input type="password" value={password} onChange={(e) => setPassword(e.target.value)} className="p-2 rounded-lg border-gray-300 dark:bg-gray-700 dark:border-gray-600 focus:ring-blue-500 focus:border-blue-500" />
        </label>
        <label className="flex flex-col">
          <span className="font-bold mb-1">{t.confirmPassword}</span>
          <input type="password" value={confirmPassword} onChange={(e) => setConfirmPassword(e.target.value)} className="p-2 rounded-lg border-gray-300 dark:bg-gray-700 dark:border-gray-600 focus:ring-blue-500 focus:border-blue-500" />
        </label>
        <button type="submit" className="p-3 bg-blue-600 text-white rounded-lg font-bold hover:bg-blue-700 transition-colors">
          {t.register}
        </button>
      </form>
      <div className="text-center text-sm">
        <span>{t.alreadyHaveAccount}</span>
        <button onClick={onLoginClick} className="text-blue-500 hover:underline mr-1">{t.login}</button>
      </div>
    </div>
  );
};

// =============================================================================
// Views/Pages
// =============================================================================

const Dashboard = ({ totalIncome, totalExpense, balance, dailyBudget, savingGoalDailyToSave, handleAddTransaction, generateAndSaveReport, glassClass, darkGlassClass, reports }) => {
  const { t, dir, currency, showMessage } = React.useContext(AppContext);
  const [description, setDescription] = useState('');
  const [amount, setAmount] = useState('');
  const [type, setType] = useState('expense');

  const handleSubmit = (e) => {
    e.preventDefault();
    if (description.trim() === '' || parseFloat(amount) <= 0) {
      showMessage('יש למלא תיאור ולציין סכום חיובי.', true);
      return;
    }
    handleAddTransaction(description, amount, type);
    setDescription('');
    setAmount('');
  };

  const currencySymbol = currencies.find(c => c.code === currency)?.symbol || '';

  return (
    <div className="flex flex-col gap-8">
      {/* Summary Section */}
      <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4 text-center">
        <div className={`p-6 ${glassClass} dark:${darkGlassClass}`}>
          <h2 className="text-xl font-semibold text-green-700 dark:text-green-300">{t.totalIncome}</h2>
          <p className="text-3xl font-bold mt-2 text-green-900 dark:text-green-100">
            {totalIncome.toFixed(2)} {currencySymbol}
          </p>
        </div>
        <div className={`p-6 ${glassClass} dark:${darkGlassClass}`}>
          <h2 className="text-xl font-semibold text-red-700 dark:text-red-300">{t.totalExpense}</h2>
          <p className="text-3xl font-bold mt-2 text-red-900 dark:text-red-100">
            {totalExpense.toFixed(2)} {currencySymbol}
          </p>
        </div>
        <div className={`p-6 ${glassClass} dark:${darkGlassClass}`}>
          <h2 className="text-xl font-semibold text-blue-700 dark:text-blue-300">{t.balance}</h2>
          <p className={`text-3xl font-bold mt-2 ${balance >= 0 ? 'text-blue-900 dark:text-blue-100' : 'text-red-900 dark:text-red-100'}`}>
            {balance.toFixed(2)} {currencySymbol}
          </p>
        </div>
        <div className={`p-6 ${glassClass} dark:${darkGlassClass}`}>
          <h2 className="text-xl font-semibold text-purple-700 dark:text-purple-300">{t.dailyBudget}</h2>
          <p className="text-3xl font-bold mt-2 text-purple-900 dark:text-purple-100">
            {dailyBudget > 0 ? dailyBudget.toFixed(2) : '0.00'} {currencySymbol}
          </p>
          <p className="text-sm mt-1 text-gray-600 dark:text-gray-400">
            ({savingGoalDailyToSave > 0 ? `+${savingGoalDailyToSave.toFixed(2)}` : '0.00'} {t.dailyToSave})
          </p>
        </div>
      </div>

      {/* Input Form Section */}
      <div className={`p-6 ${glassClass} dark:${darkGlassClass}`}>
        <h2 className="text-2xl font-semibold mb-4 text-gray-700 dark:text-gray-200">{t.addTransaction}</h2>
        <form onSubmit={handleSubmit} className="flex flex-col sm:flex-row gap-4">
          <div className="flex-grow">
            <label htmlFor="description" className="block text-sm font-medium text-gray-700 dark:text-gray-200 mb-1">
              {t.description}
            </label>
            <input
              id="description"
              type="text"
              value={description}
              onChange={(e) => setDescription(e.target.value)}
              placeholder={t.description}
              className="w-full px-4 py-2 border border-gray-300 rounded-lg shadow-sm focus:outline-none focus:ring-2 focus:ring-blue-500 bg-white/50 dark:bg-gray-700/50"
              required
            />
          </div>
          <div className="flex-grow">
            <label htmlFor="amount" className="block text-sm font-medium text-gray-700 dark:text-gray-200 mb-1">
              {t.amount} ({currencySymbol})
            </label>
            <input
              id="amount"
              type="number"
              value={amount}
              onChange={(e) => setAmount(e.target.value)}
              placeholder="0.00"
              className="w-full px-4 py-2 border border-gray-300 rounded-lg shadow-sm focus:outline-none focus:ring-2 focus:ring-blue-500 bg-white/50 dark:bg-gray-700/50"
              min="0.01"
              step="0.01"
              required
            />
          </div>
          <div className="flex-grow-0 sm:flex-grow flex items-end">
            <div className="flex-grow">
              <label className="block text-sm font-medium text-gray-700 dark:text-gray-200 mb-1">
                {t.type}
              </label>
              <div className="flex bg-white/50 dark:bg-gray-700/50 rounded-lg shadow-sm border border-gray-300 dark:border-gray-600">
                <button
                  type="button"
                  onClick={() => setType('income')}
                  className={`flex-1 flex items-center justify-center p-3 rounded-l-lg transition-all duration-200 ${
                    type === 'income' ? 'bg-green-500 text-white shadow-inner' : 'bg-white/50 dark:bg-gray-700/50 text-gray-700 dark:text-gray-200 hover:bg-gray-100 dark:hover:bg-gray-700'
                  }`}
                >
                  <Plus size={18} className={`${dir === 'rtl' ? 'ml-2' : 'mr-2'}`} />
                  {t.income}
                </button>
                <button
                  type="button"
                  onClick={() => setType('expense')}
                  className={`flex-1 flex items-center justify-center p-3 rounded-r-lg transition-all duration-200 ${
                    type === 'expense' ? 'bg-red-500 text-white shadow-inner' : 'bg-white/50 dark:bg-gray-700/50 text-gray-700 dark:text-gray-200 hover:bg-gray-100 dark:hover:bg-gray-700'
                  }`}
                >
                  <Minus size={18} className={`${dir === 'rtl' ? 'ml-2' : 'mr-2'}`} />
                  {t.expense}
                </button>
              </div>
            </div>
          </div>
          <div className="flex items-end">
            <button
              type="submit"
              className="w-full sm:w-auto px-6 py-3 bg-blue-500 text-white font-semibold rounded-lg shadow-md hover:bg-blue-600 transition-colors duration-200"
            >
              {t.add}
            </button>
          </div>
        </form>
      </div>

      {/* Reports Section */}
      <div className={`p-6 flex flex-col gap-4 ${glassClass} dark:${darkGlassClass}`}>
        <h2 className="text-2xl font-semibold text-gray-700 dark:text-gray-200">{t.budgetTables}</h2>
        <button
          onClick={generateAndSaveReport}
          className="flex items-center justify-center gap-2 p-3 bg-purple-500 text-white rounded-lg shadow-md hover:bg-purple-600 transition-colors"
        >
          <RefreshCcw size={20} />
          {t.refreshReports}
        </button>
        {reports.length === 0 ? (
          <p className="text-center italic text-gray-500 dark:text-gray-400">
            {t.noReportsYet}
          </p>
        ) : (
          <div className="flex flex-col gap-2">
            {reports.map((report) => (
              <div key={report.id} className="p-4 rounded-lg bg-gray-100/50 dark:bg-gray-700/50">
                <p className="font-bold">{report.title}</p>
                <p className="text-sm">{report.body}</p>
              </div>
            ))}
          </div>
        )}
      </div>
    </div>
  );
};

const TransactionList = ({ transactions, handleDeleteTransaction, glassClass, darkGlassClass }) => {
  const { t, dir, currency } = React.useContext(AppContext);
  const currencySymbol = currencies.find(c => c.code === currency)?.symbol || '';

  return (
    <div className={`p-6 ${glassClass} dark:${darkGlassClass}`}>
      <h2 className="text-2xl font-semibold mb-4 text-gray-700 dark:text-gray-200">{t.transactions}</h2>
      {transactions.length === 0 ? (
        <p className="text-gray-500 dark:text-gray-400 text-center italic">
          {t.noTransactions}
        </p>
      ) : (
        <div className="overflow-x-auto">
          <table className="min-w-full table-auto">
            <thead>
              <tr className="bg-gray-200/50 dark:bg-gray-700/50 text-gray-600 dark:text-gray-300 uppercase text-sm leading-normal rounded-t-lg">
                <th className={`py-3 px-6 text-${dir === 'rtl' ? 'right' : 'left'} rounded-tl-lg`}>{t.description}</th>
                <th className="py-3 px-6 text-left">{t.type}</th>
                <th className="py-3 px-6 text-left">{t.amount}</th>
                <th className="py-3 px-6 text-center rounded-tr-lg">{t.delete}</th>
              </tr>
            </thead>
            <tbody className="text-gray-600 dark:text-gray-300 text-sm font-light">
              {transactions.map((t) => (
                <tr
                  key={t.id}
                  className="border-b border-gray-200 dark:border-gray-700 hover:bg-gray-100/50 dark:hover:bg-gray-700/50 transition-colors duration-200"
                >
                  <td className={`py-3 px-6 text-${dir === 'rtl' ? 'right' : 'left'} whitespace-nowrap font-medium`}>
                    {t.description}
                  </td>
                  <td className="py-3 px-6 text-left">
                    <span
                      className={`py-1 px-3 rounded-full text-xs font-semibold ${
                        t.type === 'income' ? 'bg-green-200 text-green-700 dark:bg-green-700 dark:text-green-200' : 'bg-red-200 text-red-700 dark:bg-red-700 dark:text-red-200'
                      }`}
                    >
                      {t.type === 'income' ? t.income : t.expense}
                    </span>
                  </td>
                  <td className="py-3 px-6 text-left">
                    <span className="font-bold text-base">
                      {t.amount.toFixed(2)} {currencySymbol}
                    </span>
                  </td>
                  <td className="py-3 px-6 text-center">
                    <button
                      onClick={() => handleDeleteTransaction(t.id)}
                      className="text-red-500 hover:text-red-700 transition-colors duration-200"
                      title={t.delete}
                    >
                      <Trash2 size={20} />
                    </button>
                  </td>
                </tr>
              ))}
            </tbody>
          </table>
        </div>
      )}
    </div>
  );
};

const SettingsModal = ({ onDismiss }) => {
  const { t, theme, setTheme, transparent, setTransparent, backgroundUrl, setBackgroundUrl, font, setFont, lang, setLang, currency, setCurrency, tipsEnabled, setTipsEnabled, saveSetting, dir, userId, auth, totalBudgetAmount, setTotalBudgetAmount, budgetPeriodDays, setBudgetPeriodDays, budgetStartDate, setBudgetStartDate, leftoverAmount, setLeftoverAmount, requestNotificationPermission, currencies } = React.useContext(AppContext);
  const [activeTab, setActiveTab] = useState('design');
  const fileInputRef = useRef(null);

  const handleFileUpload = (event) => {
    const file = event.target.files[0];
    if (file) {
      const reader = new FileReader();
      reader.onloadend = () => {
        setBackgroundUrl(reader.result);
        saveSetting('backgroundUrl', reader.result);
        setTransparent(true); // הפעלת מצב שקוף אוטומטית בעת העלאת תמונה
        saveSetting('transparent', true);
      };
      reader.readAsDataURL(file);
    }
  };

  const handleBackgroundUrlChange = (e) => {
    const url = e.target.value;
    setBackgroundUrl(url);
    saveSetting('backgroundUrl', url);
    if (url) {
      setTransparent(true); // הפעלת מצב שקוף אוטומטית אם יש URL
      saveSetting('transparent', true);
    }
  };

  const handleBudgetCalculation = () => {
    if (parseFloat(totalBudgetAmount) > 0 && parseFloat(budgetPeriodDays) > 0) {
      saveSetting('totalBudgetAmount', parseFloat(totalBudgetAmount));
      saveSetting('budgetPeriodDays', parseFloat(budgetPeriodDays));
      saveSetting('budgetStartDate', budgetStartDate);
      saveSetting('leftoverAmount', parseFloat(leftoverAmount) || 0); // שמירת הסכום כשהוא מומר למספר או כ-0 אם ריק
    }
  };

  return (
    <Modal onDismiss={onDismiss} title={t.settings}>
      <div className="flex flex-col sm:flex-row gap-4 h-full">
        <div className={`flex flex-row sm:flex-col gap-2 p-4 ${theme === 'dark' ? 'bg-gray-700/50' : 'bg-gray-100/50'} rounded-xl`}>
          <TabButton onClick={() => setActiveTab('design')} active={activeTab === 'design'}>
            <Palette size={20} /> {t.designSettings}
          </TabButton>
          <TabButton onClick={() => setActiveTab('budget')} active={activeTab === 'budget'}>
            <Wallet size={20} /> {t.budgetSettings}
          </TabButton>
          <TabButton onClick={() => setActiveTab('notifications')} active={activeTab === 'notifications'}>
            <Bell size={20} /> {t.notificationsSettings}
          </TabButton>
          <TabButton onClick={() => setActiveTab('language')} active={activeTab === 'language'}>
            <Globe size={20} /> {t.languageSettings}
          </TabButton>
          <TabButton onClick={() => setActiveTab('currency')} active={activeTab === 'currency'}>
            <DollarSign size={20} /> {t.currencySettings}
          </TabButton>
        </div>
        <div className="flex-1 p-4 overflow-y-auto">
          {activeTab === 'design' && (
            <div className="flex flex-col gap-4">
              <h3 className="text-xl font-bold">{t.theme}</h3>
              <div className="flex items-center gap-2">
                <button
                  onClick={() => { setTheme('light'); saveSetting('theme', 'light'); }}
                  className={`flex-1 p-3 rounded-lg flex items-center justify-center gap-2 transition-colors ${theme === 'light' ? 'bg-blue-500 text-white' : 'bg-gray-200 dark:bg-gray-700'}`}
                >
                  <Sun size={20} /> {t.lightTheme}
                </button>
                <button
                  onClick={() => { setTheme('dark'); saveSetting('theme', 'dark'); }}
                  className={`flex-1 p-3 rounded-lg flex items-center justify-center gap-2 transition-colors ${theme === 'dark' ? 'bg-blue-500 text-white' : 'bg-gray-200 dark:bg-gray-700'}`}
                >
                  <Moon size={20} /> {t.darkTheme}
                </button>
              </div>
              <label className="flex items-center gap-2 cursor-pointer">
                <input
                  type="checkbox"
                  checked={transparent}
                  onChange={(e) => { setTransparent(e.target.checked); saveSetting('transparent', e.target.checked); }}
                  className="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded focus:ring-blue-500"
                />
                <span className="font-bold">{t.transparentMode}</span>
              </label>
              <h3 className="text-xl font-bold mt-4">{t.backgroundUrl}</h3>
              <input
                type="text"
                value={backgroundUrl}
                onChange={handleBackgroundUrlChange}
                placeholder="הכנס URL של תמונה"
                className="w-full p-2 rounded-lg border-gray-300 dark:bg-gray-700 dark:border-gray-600 focus:ring-blue-500 focus:border-blue-500"
              />
              <button
                onClick={() => fileInputRef.current.click()}
                className="w-full p-3 bg-blue-500 text-white rounded-lg hover:bg-blue-600 transition-colors"
              >
                {t.uploadBackground}
              </button>
              <input type="file" ref={fileInputRef} onChange={handleFileUpload} className="hidden" />

              <h3 className="text-xl font-bold mt-4">{t.font}</h3>
              <select
                value={font}
                onChange={(e) => { setFont(e.target.value); saveSetting('font', e.target.value); }}
                className="w-full p-2 rounded-lg border-gray-300 dark:bg-gray-700 dark:border-gray-600 focus:ring-blue-500 focus:border-blue-500"
              >
                <option value="Inter">Inter</option>
                <option value="Arial">Arial</option>
                <option value="serif">Serif</option>
                <option value="monospace">Monospace</option>
              </select>
            </div>
          )}
          {activeTab === 'budget' && (
            <div className="flex flex-col gap-4">
              <h3 className="text-xl font-bold">{t.budgetSettings}</h3>
              <label className="flex flex-col">
                <span className="font-bold mb-1">{t.totalBudget}</span>
                <input type="number" value={totalBudgetAmount} onChange={(e) => setTotalBudgetAmount(e.target.value)} className="p-2 rounded-lg border-gray-300 dark:bg-gray-700 dark:border-gray-600 focus:ring-blue-500 focus:border-blue-500" />
              </label>
              <label className="flex flex-col">
                <span className="font-bold mb-1">{t.budgetPeriod}</span>
                <input type="number" value={budgetPeriodDays} onChange={(e) => setBudgetPeriodDays(e.target.value)} className="p-2 rounded-lg border-gray-300 dark:bg-gray-700 dark:border-gray-600 focus:ring-blue-500 focus:border-blue-500" />
              </label>
              <label className="flex flex-col">
                <span className="font-bold mb-1">{t.budgetStart}</span>
                <input type="date" value={budgetStartDate} onChange={(e) => setBudgetStartDate(e.target.value)} className="p-2 rounded-lg border-gray-300 dark:bg-gray-700 dark:border-gray-600 focus:ring-blue-500 focus:border-blue-500" />
              </label>
              <label className="flex flex-col">
                <span className="font-bold mb-1">{t.leftoverAmount}</span>
                <input type="number" value={leftoverAmount} onChange={(e) => setLeftoverAmount(e.target.value)} className="p-2 rounded-lg border-gray-300 dark:bg-gray-700 dark:border-gray-600 focus:ring-blue-500 focus:border-blue-500" />
              </label>
              <button onClick={handleBudgetCalculation} className="w-full p-3 bg-blue-500 text-white rounded-lg hover:bg-blue-600 transition-colors">
                {t.calculateBudget}
              </button>
            </div>
          )}
          {activeTab === 'notifications' && (
            <div className="flex flex-col gap-4">
              <h3 className="text-xl font-bold">{t.notificationsSettings}</h3>
              <button
                onClick={requestNotificationPermission}
                className="w-full p-3 bg-blue-500 text-white rounded-lg hover:bg-blue-600 transition-colors"
              >
                {t.enableNotifications}
              </button>
              <label className="flex items-center gap-2 cursor-pointer">
                <input type="checkbox" className="w-4 h-4" />
                <span className="font-bold">{t.dailyReports}</span>
              </label>
              <label className="flex items-center gap-2 cursor-pointer">
                <input type="checkbox" className="w-4 h-4" />
                <span className="font-bold">{t.weeklyReports}</span>
              </label>
              <label className="flex items-center gap-2 cursor-pointer">
                <input type="checkbox" className="w-4 h-4" />
                <span className="font-bold">{t.monthlyReports}</span>
              </label>
            </div>
          )}
          {activeTab === 'language' && (
            <div className="flex flex-col gap-4">
              <h3 className="text-xl font-bold">{t.languageSettings}</h3>
              <select
                value={lang}
                onChange={(e) => { setLang(e.target.value); saveSetting('lang', e.target.value); }}
                className="w-full p-2 rounded-lg border-gray-300 dark:bg-gray-700 dark:border-gray-600 focus:ring-blue-500 focus:border-blue-500"
              >
                {Object.keys(languages).map(key => (
                  <option key={key} value={key}>{languages[key].name}</option>
                ))}
              </select>
            </div>
          )}
          {activeTab === 'currency' && (
            <div className="flex flex-col gap-4">
              <h3 className="text-xl font-bold">{t.currencySettings}</h3>
              <select
                value={currency}
                onChange={(e) => { setCurrency(e.target.value); saveSetting('currency', e.target.value); }}
                className="w-full p-2 rounded-lg border-gray-300 dark:bg-gray-700 dark:border-gray-600 focus:ring-blue-500 focus:border-blue-500"
              >
                {currencies.map(c => (
                  <option key={c.code} value={c.code}>{c.name} ({c.symbol})</option>
                ))}
              </select>
              <div className="mt-4">
                <h4 className="font-bold">{t.currencyConverterTitle}</h4>
                <a
                  href="https://www.google.com/search?q=currency+converter"
                  target="_blank"
                  rel="noopener noreferrer"
                  className="text-blue-500 hover:underline"
                >
                  {t.currencyConverterLink}
                </a>
              </div>
            </div>
          )}
        </div>
      </div>
    </Modal>
  );
};

const NotificationsModal = ({ onDismiss }) => {
  const { t, reports } = React.useContext(AppContext);
  return (
    <Modal onDismiss={onDismiss} title={t.notifications}>
      <div className="flex flex-col gap-4 p-4">
        {reports.length === 0 ? (
          <p className="text-gray-500 dark:text-gray-400 italic text-center">{t.noReports}</p>
        ) : (
          reports.map(report => (
            <div key={report.id} className={`p-4 rounded-lg ${report.status === t.onTrack ? 'bg-green-100/50 dark:bg-green-700/50' : 'bg-red-100/50 dark:bg-red-700/50'}`}>
              <p className="font-bold">{report.title}</p>
              <p className="text-sm">{report.body}</p>
            </div>
          ))
        )}
      </div>
    </Modal>
  );
};

export default App;
